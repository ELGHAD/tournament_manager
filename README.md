# Football Tournament Manager — C++20

A console-based football tournament management system built with C++20 and CMake. The application models teams, referees, venues, matches, tournament phases, and team rankings using object-oriented programming.

![C++](https://img.shields.io/badge/C%2B%2B-20-00599C?style=flat&logo=cplusplus&logoColor=white)
![CMake](https://img.shields.io/badge/Build-CMake-064F8C?style=flat&logo=cmake&logoColor=white)
![Architecture](https://img.shields.io/badge/Design-Object--Oriented-blue?style=flat)
![Interface](https://img.shields.io/badge/Interface-Console-lightgrey?style=flat)
![License](https://img.shields.io/badge/License-Not%20specified-lightgrey?style=flat)

## Overview

Football Tournament Manager is a command-line application designed to organize and track a football tournament. It provides a central `Tournoi` class that coordinates teams, referees, venues, matches, and rankings.

The project focuses on core C++ engineering concepts, including encapsulation, separation of interface and implementation, dynamic memory management, data structures, and business-rule validation.

The application is intended as a console-based management tool rather than a graphical or web-based platform.

## Features

### Tournament Configuration

- Configure the tournament name, date, and maximum team capacity.
- Validate required resources before starting the tournament.
- Manage tournament preparation through an interactive console menu.

### Team Management

- Register and inspect teams.
- Search teams using supported criteria such as identifier, name, city, score, or ranking.
- Apply domain validation rules, including the configured minimum squad size.

### Referee Management

- Register referees and search by referee code.
- Associate referees with matches.
- Maintain a record of refereeing decisions where supported by the implementation.

### Venue Management

- Register venues with details such as name, city, owner, and capacity.
- Search venues using available criteria.

### Match Management

- Create matches through the available scheduling options.
- Represent tournament phases, including group stages and knockout rounds.
- Record match scores and update tournament standings.

### Rankings and Tournament Progression

- Award points based on match outcomes, including wins and draws.
- Recalculate team rankings after results are recorded.
- Organize teams into groups and transition to knockout phases according to the implemented tournament rules.

## Technology Stack

| Technology | Purpose |
|---|---|
| C++20 | Application language |
| CMake | Build configuration |
| `std::vector` | Collection management |
| Header files (`.h`) | Class interfaces |
| Source files (`.cpp`) | Class implementations |
| Dynamic memory management | Match object lifecycle in the tournament model |

## Architecture

The application follows an object-oriented design with separate classes for the main tournament entities.

```text
Console Interface
       |
       v
    Tournoi
       |
       +------------------+
       |        |         |
       v        v         v
     Equipe   Arbitre   Terrain
       |
       v
     Match
       |
       v
 Results and Rankings
```

### Core Classes

| Class | Responsibility |
|---|---|
| `Tournoi` | Coordinates tournament configuration, participants, matches, and rankings |
| `Equipe` | Represents a team and its tournament statistics |
| `Arbitre` | Represents a referee and associated decisions |
| `Terrain` | Stores venue information |
| `Match` | Represents a match, its participants, assigned resources, score, and phase |

The design separates class declarations from their implementations, making individual components easier to understand and maintain.

## Project Structure

```text
Football-Tournament-Manager/
├── main.cpp
├── Tournoi.h
├── Tournoi.cpp
├── Equipe.h
├── Equipe.cpp
├── Arbitre.h
├── Arbitre.cpp
├── Terrain.h
├── Terrain.cpp
├── Match.h
├── Match.cpp
└── CMakeLists.txt
```

## Getting Started

### Prerequisites

- A C++ compiler supporting C++20, such as GCC, Clang, or a compatible MSVC version.
- CMake 3.29 or later, as specified by the project configuration.

### Clone the Repository

If the repository retains its current name:

```bash
git clone https://github.com/ELGHAD/Chess-tournament.git
cd Chess-tournament
```

### Build the Application

```bash
mkdir build
cd build
cmake ..
cmake --build .
```

### Run

On Linux or macOS, if the generated executable is named `gestionTournoi`:

```bash
./gestionTournoi
```

On Windows, run the generated `gestionTournoi.exe` from its build output directory. The exact executable location may depend on the selected generator and build configuration.

The program provides an interactive console menu for managing tournament information and following matches and results.

## Engineering Concepts

### Encapsulation

Classes encapsulate their data and expose operations through public methods, helping separate internal state from external use.

### Interface and Implementation Separation

Each principal class uses a header file for its declaration and a source file for its implementation. This organization improves readability and supports modular development.

### Business-Rule Validation

The application includes validation for selected tournament constraints, such as team identifiers, squad size, and prerequisites for starting the tournament.

### Data Structures and Algorithms

Standard C++ containers support the management of tournament entities, while search and sorting operations support team lookup and ranking updates.

### Memory Management

The tournament implementation uses dynamically allocated match objects and explicit cleanup. This provides an opportunity to study object lifecycles and resource ownership in C++.

For further modernization, smart pointers such as `std::unique_ptr` would make ownership clearer and reduce the risk of memory-management errors.

## Current Scope and Limitations

This project is a console-based football tournament manager. It should not be confused with a chess tournament application.

Its current scope does not establish the presence of a graphical interface, database persistence, a web API, or automated test coverage.

The use of raw pointers also means that object ownership and cleanup deserve particular attention. Automated tests for tournament progression, score recording, and ranking calculations would improve confidence in the implementation.

## Potential Improvements

1. Replace owning raw pointers with `std::unique_ptr` where appropriate.
2. Add unit tests for ranking calculations and tournament progression.
3. Improve scheduling constraints to prevent conflicting venue or referee assignments.
4. Separate tournament rules from console input and output.
5. Add persistent storage for teams, matches, and results.
6. Introduce continuous integration to build and test the application automatically.

## Author

**Hamza Elrhadiouini**

- GitHub: [@ELGHAD](https://github.com/ELGHAD)
- Portfolio: [elghad.github.io/hamza-elrhadiouini-portfolio](https://elghad.github.io/hamza-elrhadiouini-portfolio)
