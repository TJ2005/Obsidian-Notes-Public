---
Title: DBMS Report
Status: 
marker: 
tags: 
Date: 2024.11.07
Time: 11:48
---
# Database Management System Project Report

**Project by:**
- **K057** Tejas Sahoo
- **K039** Unnat Mishra
- **K062** Uday Singh

---

## 1. Introduction

This project presents a comprehensive relational database schema designed to manage information on games, their developers and publishers, user interactions, and purchase history. Our main objective is to create a well-structured and normalized database that efficiently organizes data for easy retrieval and reduces redundancy. This database is particularly suitable for use in applications or platforms focused on gaming content, such as review sites, digital marketplaces, and leaderboards.

### Project Objectives

- **Manage Game Information**: Store details of games, their developers, publishers, and related media.
- **User Interactions**: Capture user interactions with games, including reviews, achievements, and purchases.
- **Price and Sales Tracking**: Record the price history of games to help users make informed decisions about purchases.
- **Data Integrity**: Ensure data integrity and consistency across the database with normalization and constraints.
- **Efficient Data Retrieval**: Design the schema to allow efficient retrieval of key information, supporting a variety of queries for different use cases.

### Why a Relational Database?

Relational databases provide a robust framework for organizing structured data, making them ideal for applications that require complex relationships and data integrity. With features like foreign keys, constraints, and normalization, a relational database ensures that our data remains consistent and free from unnecessary redundancy.

---

## 2. ER Diagram and Schema

In this section, we provide an **Entity-Relationship (ER) Diagram** and a detailed **database schema**. The ER diagram visualizes the entities and their relationships, while the schema defines each table, its attributes, primary and foreign keys, and constraints.
![](https://lh7-rt.googleusercontent.com/slidesz/AGV_vUdfexTbJJ5QhZc6JacoBzEY_S35rTeI0HXRy4BQvSd7dpGuUegJOekG6oYhMz-d_4_Qz8jEo-oLLVNicaIkStvg0RBIUdqPRHoCWCVF5jsMkS9xfrlmuUubLQnNrsPTkU-g2xvM-ED6F09_Am8rFQ5syFqufLs=s2048?key=4lnDaqRSwV50Sx7hEsZN9VWi)

![](https://lh7-rt.googleusercontent.com/slidesz/AGV_vUdTQ-i-ShqQr8W3pmMm-GXJCUqbAXQMKSacEd6KKtcWL7qH9Ia2fcXwVJzAh3JvmRrZcu5kqiB8NHubSSV2IRVoA_eGnip2GC1gZMHP2QHxUbL2ekgmSMhl84i8ocz0S3Ly7IJU0hpnqUmN5Xe8SfPzI_PFKp8=s2048?key=4lnDaqRSwV50Sx7hEsZN9VWi)

---

## 3. Deliverables

The database schema offers the following tables and features to fulfill the project objectives:

1. **Games**  
   - Stores essential information on games, including `name`, `release_date`, `publisher_id`, and `developer_id`.
   - Enables tracking of each game’s genre and association with developers and publishers.

2. **Publishers and Developers**  
   - `Publishers` table stores data about the companies responsible for publishing games, such as `publisher_name` and `publisher_country`.
   - `Developers` table captures details of developers, including `developer_name`, `developer_rating`, and `developer_country`.

3. **Price History**  
   - Tracks changes in the price of each game over time, providing information such as `price`, `discount`, and `timestamp`.
   - Helps users view price trends and decide the best time to make purchases.

4. **DLC (Downloadable Content)**  
   - Manages additional content packages associated with each game, including `price`, `currency`, and `discount`.
   - Works with the `Purchases` table to record which DLC packages users have purchased.

5. **User Interactions**  
   - **Reviews**: Records user reviews of games, including `review_text`, `review_date`, and `rating`, allowing for detailed user feedback.
   - **Achievements**: Tracks each user’s achievements in a game, including `play_time` and `achievements_unlocked`, supporting a richer user experience.
   - **Leaderboard Ranking**: Stores ranking information for games, providing insight into game popularity or performance.

6. **Sequels and Relationships**  
   - The `SequelGames` table establishes relationships between original games and their sequels, allowing users to explore game series.

7. **Media Management**  
   - Stores media associated with games, such as `screenshots`, `video`, and `trailer` links, enhancing the user experience with multimedia elements.

8. **Users**  
   - Manages user information, including `username`, `email`, `last_login`, and `created_at`, providing a foundation for personalizing interactions within the platform.

9. **Purchases**  
   - Records information on DLC purchases made by users, linking to both `Users` and `DLC` tables, to maintain a history of transactions.

---

## 4. Normalization

Normalization reduces redundancy and ensures that data is organized efficiently. Below, we discuss the normalization levels applied to the schema:

### 1. First Normal Form (1NF)
- **Definition**: A table is in 1NF if all columns contain atomic values and each row is unique.
- **Application**: All tables have atomic values (e.g., `publisher_name` in `Publishers` and `username` in `Users`). Each table has a primary key to ensure uniqueness.

### 2. Second Normal Form (2NF)
- **Definition**: A table is in 2NF if it is in 1NF and every non-key attribute is fully dependent on the primary key.
- **Application**: Tables with single-column primary keys, like `Publishers` and `Games`, satisfy 2NF, as all non-key attributes depend on the primary key. Composite-key tables, such as `Achievements`, also satisfy 2NF, as non-key attributes depend on the full composite key.

### 3. Third Normal Form (3NF)
- **Definition**: A table is in 3NF if it is in 2NF and has no transitive dependencies.
- **Application**: Each non-key attribute in our schema depends only on the primary key, with no transitive dependencies (e.g., in `Reviews`, `review_text` and `rating` depend only on the primary key composed of `user_id` and `game_id`).

### 4. Boyce-Codd Normal Form (BCNF)
- **Definition**: BCNF is a stricter version of 3NF, where every determinant is a candidate key.
- **Application**: All tables meet BCNF standards, as every determinant is a candidate key.

### 5. Fourth Normal Form (4NF)
- **Definition**: A table is in 4NF if it is in BCNF and has no multi-valued dependencies.
- **Application**: By organizing data into tables like `GamePlatformAssociation`, multi-valued dependencies are avoided, ensuring that each table contains atomic values.

---

## 5. SQL Queries

This section provides sample SQL queries for retrieving data based on our schema.

### Query 1: Retrieve all reviews for a specific game
```sql
SELECT Users.username, Reviews.review_text, Reviews.rating
FROM Reviews
JOIN Users ON Reviews.user_id = Users.user_id
WHERE Reviews.game_id = 1;
```

### Query 2: List all games developed by a specific developer
```sql
SELECT Games.name
FROM Games
WHERE Games.developer_id = 2;
```

### Query 3: Get leaderboard rankings for all games
```sql
SELECT Games.name, LeaderboardRanking.ranking
FROM LeaderboardRanking
JOIN Games ON LeaderboardRanking.game_id = Games.game_id
ORDER BY LeaderboardRanking.ranking ASC;
```

### Query 4: Find the price history for a specific game
```sql
SELECT PriceHistory.price, PriceHistory.discount, PriceHistory.timestamp
FROM PriceHistory
WHERE PriceHistory.game_id = 3
ORDER BY PriceHistory.timestamp DESC;
```

### Query 5: List all users who purchased a specific DLC package
```sql
SELECT Users.username
FROM Purchases
JOIN Users ON Purchases.user_id = Users.user_id
WHERE Purchases.package_id = 105;
```

---
## 6. Example Data for understanding
![](https://lh7-rt.googleusercontent.com/slidesz/AGV_vUeRhKKhrNCJvIexXJ2AD4_yzQd8BkoGHAN5Mc4Ilr03_QbmnVPjFslC4-DnIsYdfcIEHOp1T7MacB6bygQtpS6dTf2Wg6HwFVQvKPWS60BBCEF-6HRf4LxsUWrb90sf3cWyx11P=s2048?key=4lnDaqRSwV50Sx7hEsZN9VWi)![](https://lh7-rt.googleusercontent.com/slidesz/AGV_vUfUne4v1UwOvOMuuiu5wEWcGlQ4xhNwALls4ml0LYxHPC4qskoEOP1ko5zIvUw1UD7TnIPKZVVVEZS-9kjOU1a7_t2nvmi9v8TCV5mL28phwf4e1HAR8xRMxBIOZN5Bl_RzHhTWiA=s2048?key=4lnDaqRSwV50Sx7hEsZN9VWi)![](https://lh7-rt.googleusercontent.com/slidesz/AGV_vUctTz9LRLTXtcbTACPNQks1qKnI5yYrtP1RuH_WVOQH82pJjE5VzfloiBoZV1mbtFJZMAi4nLF2qpjEg8MTvhfZxghOsCg_bvCLLb1WLx2gdMcRCYjNAx1A-JKThP_9Ua__RAmjsA=s2048?key=4lnDaqRSwV50Sx7hEsZN9VWi)
**![](https://lh7-rt.googleusercontent.com/slidesz/AGV_vUetCl9NLOa5VH6HbWZGRd6_7XeqKfJop5wI9KzL7kVfc0zQjLD0zvlfGKQXqpxJNEv6XQdXxu70YVTbmd-Xw4oTFU3qayuXfnTH_wshdrCYZuitR2aPOW9DjaBE34RxfY-CYgXskg=s2048?key=4lnDaqRSwV50Sx7hEsZN9VWi)
![](https://lh7-rt.googleusercontent.com/slidesz/AGV_vUc9F1PloifNrPhwHPkicq-rysLWhkRmWoKNkHlRdhe_M0pEHITr4D0DtwmAHIzfpw2k4Zu5Tir1a8Do3sTmXU9K1NeJ15_qqxWvkkrh7FG6kAl3CmqiBk0csi4obH3YgHFazI-K=s2048?key=4lnDaqRSwV50Sx7hEsZN9VWi)