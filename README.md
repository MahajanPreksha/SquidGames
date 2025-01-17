# Squid Games-themed MongoDB Challenge: "The Survival Query"

In this Squid Game-inspired challenge, participants will play the role of contestants in a fictional "Data Survival Game." Each query they solve keeps them alive in the game, while incorrect or delayed responses risk "elimination".

## About the Dataset
The dataset revolves around players, games, eliminations and prize pool.

## Collections and their Schema

### 1. `players` Collection

| Field         | Type     | Description                                         |
|---------------|----------|-----------------------------------------------------|
| `player_id`   | String   | A unique identifier for each player (e.g., "P001"). |
| `name`        | String   | The player's full name (e.g., "John Doe").          |
| `age`         | Integer  | The player's age in years (e.g., 29).               |
| `debt`        | Integer  | The amount of debt the player has (e.g., 500000).   |
| `status`      | String   | The player's current status: `"active"` or `"eliminated"`. |

### 2. `games` Collection

| Field         | Type     | Description                                                   |
|---------------|----------|---------------------------------------------------------------|
| `game_id`     | String   | A unique identifier for each game (e.g., "G001").             |
| `name`        | String   | The name of the game (e.g., "Red Light Green Light").         |
| `difficulty`  | Integer  | A difficulty level on a scale of 1 to 10 (e.g., 8).           |
| `max_players` | Integer  | The maximum number of players allowed in the game (e.g., 200).|

### 3. `eliminations` Collection

| Field           | Type     | Description                                                    |
|------------------|----------|----------------------------------------------------------------|
| `elimination_id` | String   | A unique identifier for each elimination event (e.g., "E001").|
| `player_id`      | String   | The unique identifier of the eliminated player (e.g., "P010").|
| `game_id`        | String   | The unique identifier of the game where elimination occurred. |
| `reason`         | String   | The reason for the player's elimination (e.g., "Crossed the line").|

### 4. `prize_pool` Collection

| Field               | Type     | Description                                                              |
|---------------------|----------|--------------------------------------------------------------------------|
| `current_pool`      | Integer  | The total prize pool value after the game (e.g., 456000000).             |
| `game_id`           | String   | The unique identifier of the game linked to this prize pool (e.g., "G003").|
| `eliminated_players`| Integer  | The total number of players eliminated in the corresponding game (e.g., 45).|

## Challenge Format
Each query is tied to a game or event in the Squid Game storyline.

The goal is to ensure contestants progress through the rounds by correctly answering queries.

## Queries

**Beginner Level**

1. Find Active Players: Retrieve all players who are still active in the game.
2. Count Number of Players: Count the total number of players.
3. Find Eliminations in Game No. 3: Find all eliminations in G003.

**Intermediate Level**

4. Players in Specific Age Range: Find players who are between 25 and 35 years old.
5. Find Games With Difficulty Above 7: Find games with difficulty greater than 7.
6. Find Most Common Elimination Reason: Group by `reason` and count the number of times each reason appears, sorting by frequency.

**Expert Level**

7. Top 5 Players with the Highest Debt Find the top 5 players based on the amount of debt they owe.
8. Players with Odd Age: Find players whose age is odd.

**Advanced Level**

9. Game with Maximum Contribution towards Prize Pool: Find the game that contributed the most to the prize pool.
10. Player with Maximum Debt in each Age Group: Find the player with the maximum debt in each age group.

<hr>
