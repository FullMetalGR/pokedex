# Pokedex CLI

A command-line interface Pokedex application built with TypeScript that allows you to explore Pokemon locations, catch Pokemon, and manage your collection.

## Features

- **Location Exploration**: Browse Pokemon locations and explore specific areas
- **Pokemon Catching**: Attempt to catch Pokemon with realistic catch rates based on their base experience
- **Caching System**: Intelligent caching for faster repeated requests
- **Pokedex Management**: Track and view your caught Pokemon
- **Interactive CLI**: User-friendly command-line interface

## Commands

### `help`
Displays all available commands and their descriptions.

### `exit`
Exits the Pokedex application.

### `map`
Displays the next 20 location areas. Use this to browse through different Pokemon locations.

### `mapb`
Displays the previous 20 location areas. Navigate backwards through the location list.

### `explore <location_name>`
Explores a specific location area and shows all Pokemon found there.

**Example:**
```
pokedex > explore pastoria-city-area
Exploring pastoria-city-area...
Found Pokemon:
 - tentacool
 - tentacruel
 - magikarp
 - gyarados
 - remoraid
 - octillery
 - wingull
 - pelipper
 - shellos
 - gastrodon
```

### `catch <pokemon_name>`
Attempts to catch a Pokemon by name. The catch rate is based on the Pokemon's base experience - stronger Pokemon are harder to catch.

**Example:**
```
pokedex > catch pikachu
Throwing a Pokeball at pikachu...
pikachu was caught!
You may now inspect it with the inspect command.

pokedex > catch mewtwo
Throwing a Pokeball at mewtwo...
mewtwo escaped!
```

### `inspect <pokemon_name>`
View detailed information about a Pokemon you've caught.

### `pokedex`
Shows all Pokemon in your collection.

**Example:**
```
pokedex > pokedex
Your Pokedex:
 - pikachu
 - squirtle
 - charmander
```

## Installation

1. Clone the repository:
```bash
git clone https://github.com/FullMetalGR/pokedex.git
cd pokedex
```

2. Install dependencies:
```bash
npm install
```

3. Build the project:
```bash
npm run build
```

4. Run the application:
```bash
npm start
```

## Development

- **Build**: `npm run build`
- **Development mode**: `npm run dev`
- **Run tests**: `npm test`

## Technical Details

### Architecture
- **TypeScript**: Full type safety throughout the application
- **Caching System**: Automatic cache cleanup with configurable intervals
- **API Integration**: Uses the PokeAPI for Pokemon and location data
- **State Management**: Centralized state for managing user data and pagination

### Caching
The application includes an intelligent caching system that:
- Caches API responses for 5 minutes by default
- Automatically cleans up old cache entries
- Provides faster response times for repeated requests
- Logs when cached vs fresh data is used

### Catch Mechanics
Pokemon catch rates are calculated based on their base experience:
- Higher base experience = harder to catch
- Uses a realistic formula that provides reasonable chances
- Minimum 10% catch rate, maximum 90% catch rate

## API Endpoints Used

- **Locations**: `https://pokeapi.co/api/v2/location-area`
- **Location Details**: `https://pokeapi.co/api/v2/location-area/{name}`
- **Pokemon**: `https://pokeapi.co/api/v2/pokemon/{name}`

## Contributing

This is a boot.dev project. Feel free to submit issues and enhancement requests!

## License

ISC License

## Ideas for Extending the Project

Here are just a few ideas to extend this project:

- Implement the repl Node module
- Simulate battles between pokemon
- Add more unit tests
- Refactor your code to organize it better and make it more testable
- Keep pokemon in a "party" and allow them to level up
- Allow for pokemon that are caught to evolve after a set amount of time
- Persist a user's Pokedex to disk so they can save progress between sessions
- Use the PokeAPI to make exploration more interesting. For example, rather than typing the names of areas, maybe you are given choices of areas and just type "left" or "right"
- Random encounters with wild pokemon
- Adding support for different types of balls (Pokeballs, Great Balls, Ultra Balls, etc), which have different chances of catching pokemon
