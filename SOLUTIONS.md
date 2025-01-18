# Solutions to the Challenge:

## Beginner Level

1. Find Active Players: Retrieve all players who are still active in the game.

```javascript
db.players.find({ status: "active" })
```

2. Count Number of Players: Count the total number of players.

```javascript
db.players.countDocuments()
```

3. Find Eliminations in Game No. 3: Find all eliminations in G003.

```javascript
db.eliminations.find({ game_id: "G003" })
```

## Intermediate Level

4. Players in Specific Age Range: Find players who are between 25 and 35 years old.

```javascript
db.players.find({ age: { $gte: 25, $lte: 35 } })
```

5. Find Games With Difficulty Above 7: Find games with difficulty greater than 7.

```javascript
db.games.find({ difficulty: { $gt: 7 } })
```

6. Find Most Common Elimination Reason: Group by `reason` and count the number of times each reason appears, sorting by frequency.

```javascript
db.eliminations.aggregate([
  { $group: { _id: "$reason", count: { $sum: 1 } } },
  { $sort: { count: -1 } }
])
```

## Expert Level

7. Top 5 Players with the Highest Debt Find the top 5 players based on the amount of debt they owe.

```javascript
db.players.find().sort({ debt: -1 }).limit(5)
```

8. Players with Odd Age: Find players whose age is odd.

```javascript
db.players.find({ age: { $mod: [2, 1] } })
```

## Advanced Level

9. Game with Maximum Contribution towards Prize Pool: Find the game that contributed the most to the prize pool.

```javascript
db.prize_pool.aggregate([
  { $sort: { current_pool: -1 } },
  { $limit: 1 }
])
```

10. Player with Maximum Debt in each Age Group: Find the player with the maximum debt in each age group.

```javascript
db.players.aggregate([
  { $group: { _id: "$age", max_debt: { $max: "$debt" }, player: { $first: "$name" } } },
  { $sort: { _id: 1 } }
])
```
