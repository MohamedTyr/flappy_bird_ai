# Flappy Bird AI - NEAT

This project implements the classic **Flappy Bird** game using Python and Pygame, with an added twist: the bird is controlled by a neural network that learns to play the game using the **NEAT** (NeuroEvolution of Augmenting Topologies) algorithm. The AI evolves over generations to improve its performance, trying to navigate the bird through pipes and maximize its score.



https://github.com/user-attachments/assets/7516b632-2afe-461a-822c-84f0c544e648


## Features

- **Flappy Bird Gameplay**: Classic side-scrolling mechanics with obstacles (pipes) that the bird must avoid.
- **Neural Network AI**: Birds are controlled by a neural network that learns how to jump and avoid obstacles.
- **Neuroevolution with NEAT**: The project uses the NEAT algorithm to evolve neural networks over generations to optimize the bird's performance.
- **Fitness-based Evaluation**: The neural networks are trained based on how far they fly and how many pipes they pass.
- **Real-time Display**: Watch the birds evolve and improve their gameplay over multiple generations.

## Getting Started

### Prerequisites

To run this project, you'll need:

- **Python 3.7+**
- **Pygame**
- **NEAT-Python** library

### Installation

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/MohamedTyr/flappy_bird_ai
   cd flappy-bird-ai
   ```

2. **Install Dependencies**:
   Install the required Python packages via pip:

   ```bash
   pip install pygame neat-python
   ```

3. **Run the Game**:
   Once the dependencies are installed, you can start the game with:
   ```bash
   python flappy_bird.py
   ```

## Project Structure

```
.
├── imgs/                      # Game assets
├── config-feedforward.txt     # NEAT configuration file
└── flappy_bird.py             # Main script to run the game
```

### Key Files

- **`flappy_bird.py`**: The main game script. It handles the game loop, rendering, bird movement, pipe generation, and NEAT AI integration.
- **`config-feedforward.txt`**: NEAT configuration file used to define parameters like population size, mutation rates, and fitness function details.
- **`imgs/`**: Contains all the game’s graphical assets (bird, pipe, background, etc.).

## How It Works

### Game Mechanics

The game follows the classic Flappy Bird mechanics:

- The bird automatically falls due to gravity.
- When the player (or AI) presses a key (or the AI activates), the bird jumps upward.
- Pipes generate randomly and move from right to left across the screen, and the bird must avoid colliding with them.

### NEAT Algorithm

The NEAT algorithm controls the bird’s actions. It evolves a population of neural networks, where each network controls one bird. The bird makes decisions (to jump or not) based on:

- Its current vertical position.
- The distance to the next pipe.
- The gap between the pipe’s top and bottom.

Each bird is evaluated based on its **fitness** (the further the bird flies and the more pipes it passes, the higher the fitness score). After each generation, the networks evolve, selecting the best performers and mutating them to create new ones, with the goal of improving performance in the next generation.

### Fitness Evaluation

- Birds gain fitness points based on how long they survive and how many pipes they pass.
- Collisions with pipes or the ground reduce fitness and eliminate the bird from the current generation.

## Customization

### Adjusting NEAT Configuration

To tweak the AI’s performance, you can modify the `config-feedforward.txt` file. Some key parameters include:

- **`pop_size`**: The size of the population (number of birds per generation).
- **`fitness_threshold`**: The fitness required for a network to be considered successful.
- **`max_stagnation`**: The number of generations with no improvement before stopping.

### Drawing Debug Lines

If you want to visualize the bird's decision-making process, you can enable debug lines by setting `DRAW_LINES = True` in the `flappy_bird.py` file. This will draw lines between the bird and the next pipe, showing the inputs the neural network is using.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

### Enjoy watching AI learn to master the Flappy Bird game! 🐦
