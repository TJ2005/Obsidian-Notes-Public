[[Lab]] [[project]]

The website you provided, [SteamDB](https://steamdb.info/), is a third-party tool that tracks data related to the Steam platform. It aggregates information about games, packages, prices, and other Steam-related statistics. The specific details of the database schema used by SteamDB are proprietary and not publicly disclosed. However, we can speculate on the type of database and provide a possible relational schema based on the functionalities of the website.

### Database Type
SteamDB likely uses a relational database, such as PostgreSQL or MySQL, given the structured nature of the data (games, packages, prices, etc.) and the need for complex queries and indexing.
### Changes if any:
Redudancies

### Speculative Relational Schema

#### 1. **Users**
   - `user_id` (Primary Key)
   - `username`
   - `email`
   - `password_hash`
   - `created_at`
   - `last_login`

#### 2. **Games**
   - `game_id` (Primary Key)
   - `name`
   - `developer_id` (Foreign Key)
   - `publisher_id` (Foreign Key)
   - `release_date`
   - `steam_app_id` (Unique)
   - `platform`
   - `genre_id` (Foreign Key)

#### 3. **Developers**
   - `developer_id` (Primary Key)
   - `name`
   - `website`
   - `country`

#### 4. **Publishers**
   - `publisher_id` (Primary Key)
   - `name`
   - `website`
   - `country`

#### 5. **Genres**
   - `genre_id` (Primary Key)
   - `genre_name`

#### 6. **Packages**
   - `package_id` (Primary Key)
   - `game_id` (Foreign Key)
   - `price`
   - `discount`
   - `currency`
   - `last_updated`

#### 7. **Price_History**
   - `price_history_id` (Primary Key)
   - `package_id` (Foreign Key)
   - `price`
   - `discount`
   - `timestamp`

#### 8. **Platforms**
   - `platform_id` (Primary Key)
   - `platform_name`

#### 9. **Game_Platforms**
   - `game_platform_id` (Primary Key)
   - `game_id` (Foreign Key)
   - `platform_id` (Foreign Key)

#### 10. **Reviews**
   - `review_id` (Primary Key)
   - `game_id` (Foreign Key)
   - `user_id` (Foreign Key)
   - `rating`
   - `review_text`
   - `review_date`

#### 11. **Game_Tags**
   - `game_id` (Foreign Key)
   - `tag_id` (Foreign Key)

#### 12. **Tags**
   - `tag_id` (Primary Key)
   - `tag_name`

### Explanation
- **Users** table stores information about the users who may have accounts on SteamDB.
- **Games** table stores basic information about each game.
- **Developers** and **Publishers** tables store details about the entities responsible for creating and distributing the games.
- **Genres** table stores different game genres (e.g., Action, Adventure).
- **Packages** table contains information about different purchase options for each game, including pricing.
- **Price_History** tracks the changes in the prices of packages over time.
- **Platforms** and **Game_Platforms** store the platforms on which a game is available (e.g., Windows, macOS).
- **Reviews** contain user-submitted reviews of games.
- **Tags** and **Game_Tags** are used to categorize games with tags like "Multiplayer," "Singleplayer," etc.

This schema is a speculative example and may not reflect the exact implementation used by SteamDB, but it represents a reasonable approach for handling the type of data the site works with.