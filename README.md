# Wumpus World Game

A classic AI problem environment implemented as an interactive web game. Explore a mysterious cave system, avoid deadly dangers, and find the gold!

## Features

- 🎮 Interactive 4x4 grid-based cave system (configurable 5x5 or 6x6)
- 🧙‍♂️ Agent navigation with 4-directional movement
- 💨 Perception system with stench, breeze, and glitter indicators
- 👹 Wumpus monster to avoid or eliminate
- 🕳️ Dangerous pits to navigate around
- 💰 Gold to collect and escape with
- 🏹 Arrow to shoot the Wumpus
- 🎯 Scoring system based on actions and objectives
- 📊 Multiple difficulty levels (Easy, Medium, Hard)
- 👁️ Player view and God mode for exploring
- ⌨️ Keyboard controls for accessibility

## Getting Started

### Prerequisites
- Node.js 18+ and npm

### Installation

```bash
# Install dependencies
npm install

# Start development server
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview
```

## How to Play

### Objective
Find the gold 💰 and return to the starting position (0,0) to win!

### Controls
- **Arrow Keys** or **WASD** - Move in four directions
- **G** - Grab gold (when in same cell)
- **F** - Fire arrow (kills Wumpus)
- **C** - Climb out (only at starting position with gold)

### Percepts (Environmental Clues)
- 💨 **Stench** - Wumpus is in an adjacent cell
- 🌬️ **Breeze** - Pit is in an adjacent cell
- ✨ **Glitter** - Gold is in your current cell

### Dangers
- 👹 **Wumpus** - Eats you on contact (unless killed with arrow)
- 🕳️ **Pits** - Fatal fall if you enter
- 💥 **Walls** - Can't move outside the grid

## Scoring System

| Action | Points |
|--------|--------|
| Find Gold | +1000 |
| Kill Wumpus | +500 |
| Exit with Gold | +1000 bonus |
| Each Move | -1 |
| Fire Arrow | -10 |
| Death | -1000 |

## Difficulty Levels

- **Easy**: 4x4 grid, 2 pits, Wumpus location hint
- **Medium**: 4x4 grid, 3 pits (default)
- **Hard**: 5x5 grid, 4 pits

## Project Structure

```
src/
├── components/
│   ├── GameBoard.tsx      # Main game container
│   ├── Grid.tsx           # Game grid display
│   ├── Cell.tsx           # Individual cell component
│   ├── ControlPanel.tsx   # Game controls
│   └── StatusMessages.tsx # Message display
├── hooks/
│   └── useGame.ts         # Game state management hook
├── utils/
│   └── gameLogic.ts       # Game mechanics and logic
├── constants/
│   └── gameConfig.ts      # Game configuration
├── types/
│   └── index.ts           # TypeScript type definitions
├── App.tsx                # Main app component
└── main.tsx               # React entry point
```

## Technologies Used

- **React** - UI framework
- **TypeScript** - Type safety
- **Tailwind CSS** - Styling
- **Vite** - Build tool
- **Lucide React** - Icons (optional)

## Game Example

```
    0   1   2   3
  ┌───┬───┬───┬───┐
3 │   │ 💨│   │👹 │
  ├───┼───┼───┼───┤
2 │🌬️│🕳️│💨│   │
  ├───┼───┼───┼───┤
1 │   │🌬️│💰│   │
  ├───┼───┼───┼───┤
0 │🧙‍♂️│   │🌬️│   │
  └───┴───┴───┴───┘

Percepts: 🌬️ Breeze
Score: -1 | Moves: 1
```

## Tips for Playing

1. **Map the Cave**: Use percepts to deduce where dangers are
2. **Avoid Blind Moves**: Check for stench and breeze before moving
3. **Plan Your Path**: Plot a safe route to the gold
4. **Use God Mode**: Toggle to see the full map for learning
5. **Manage Your Arrow**: You only have one shot!

## Future Enhancements

- Multiple Wumpus monsters
- More arrows
- Larger grid sizes (6x6, 8x8)
- Time limits
- Power-ups (torch, map, immunity)
- AI autopilot mode
- Multiplayer gameplay
- Procedurally generated levels
- Sound effects and animations
- Online leaderboard

## Learning Resources

This game teaches AI concepts including:
- **Perception** - Gathering environmental information
- **Reasoning** - Making inferences from percepts
- **Planning** - Deciding action sequences
- **Knowledge Representation** - Maintaining world beliefs
- **Uncertainty** - Handling incomplete information

Based on the classic Wumpus World problem from "Artificial Intelligence: A Modern Approach" by Russell & Norvig.

## License

MIT License

## Acknowledgments

- Original Wumpus World concept from Russell & Norvig
- Classic AI problem for teaching logical reasoning
