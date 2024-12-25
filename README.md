# Celestial Database Project

This project is a relational database designed to catalog and organize information about celestial bodies in our universe. It was created as part of the [**Relational Database Course**](https://www.freecodecamp.org/learn/relational-database/) from FreeCodeCamp.

## Project Overview
The Celestial Database allows users to store and query information about various types of celestial objects, such as planets, stars, moons, and asteroids. It aims to provide an efficient and normalized data structure to support astronomical research and education.

## Features
- **Categorization of Celestial Bodies**: Includes planets, stars, moons, comets, and more.
- **Relational Structure**: Proper normalization of tables with primary and foreign keys.
- **Query Capability**: SQL queries to retrieve detailed information and relationships between celestial objects.
- **Scalability**: Designed to handle the addition of new celestial objects and categories.

## Database Schema
The database contains the following tables:


### 1. `galaxy`
Stores information about galaxies.

- `galaxy_id` (integer): Unique identifier for the galaxy.
- `name` (varchar): Name of the galaxy.
- `age_in_millions_of_years` (numeric): Age of the galaxy in millions of years.
- `spiral` (boolean): Indicates if the galaxy is spiral.
- `diameter_in_light_years` (integer): Diameter of the galaxy in light-years.

### 2. `star`
Stores information about stars.

- `star_id` (integer): Unique identifier for the star.
- `name` (varchar): Name of the star.
- `num_of_planets` (integer): Number of planets around the star.
- `galaxy_id` (integer): Identifier of the galaxy where the star is located.
- `weight_in_solar_masses` (numeric): Weight of the star in solar masses.


### 3. `planet`
Stores information about planets.

- `planet_id` (integer): Unique identifier for the planet.
- `name` (varchar): Name of the planet.
- `has_moon` (boolean): Indicates if the planet has moon(s).
- `year_of_discovery` (integer): Year of discovery.
- `star_id` (integer): Identifier of the star the planet orbits.

### 4. `moon`
Stores information about moons.

- `moon_id` (integer): Unique identifier for the moon.
- `name` (varchar): Name of the moon.
- `diameter_in_kilometers` (numeric): Diameter of the moon in kilometers.
- `year_of_discovery` (integer): Year of discovery.
- `planet_id` (integer): Identifier of the planet the moon belongs to.

### 5. `asteroid`
Stores information about asteroids.

- `asteroid_id` (integer): Unique identifier for the asteroid.
- `name` (varchar): Name of the asteroid.
- `orbital_classification` (text): Orbital classification of the asteroid.
- `year_of_discovery` (integer): Year of discovery.

## Installation
1. Clone the repository:
   ```bash
   https://github.com/apenas-will/Celestial-Bodies-Database.git
   ```
2. Navigate to the project directory:
   ```bash
   cd Celestial-Bodies-Database
   ```
3. Load the database schema into your SQL server (compatible with PostgreSQL, MySQL, or SQLite).
   ```bash
   psql -U postgres < universe.sql
   ```

## Usage
- Use SQL queries to interact with the database.
- Add new data to the database using SQL `INSERT` statements or a dedicated API (if implemented).
- Perform complex queries to analyze relationships, such as finding all moons orbiting a specific planet or listing celestial bodies in a star system.

## Example Query
Find all planets of the solar system:
```sql
SELECT name
FROM planet
WHERE star_id = 1;
```

## Contributing
Contributions are welcome! Please fork the repository and submit a pull request with your improvements.

## License
This project is licensed under the [MIT License](LICENSE).

---

### Acknowledgments
This project was made for the FreeCodeCamp Relational Database Course. Special thanks to the open-source community for providing valuable tools and resources.