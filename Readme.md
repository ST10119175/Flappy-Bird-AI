# Flappy Bird AI using NEAT

This project implements an AI that learns to play Flappy Bird using the NEAT (NeuroEvolution of Augmenting Topologies) algorithm. The AI evolves neural networks through natural selection to master the game mechanics.

## Project Overview

Flappy Bird AI uses the NEAT algorithm to evolve a population of neural networks that control birds navigating through pipes. Each generation of birds learns from the previous one, with the most successful birds passing on their traits to the next generation.

![Flappy Bird AI Demo](imgs/demo.png)

## Features

- **AI Learning**: Uses NEAT to evolve neural networks that improve over generations
- **Visual Display**: Shows game progress with score and generation counter
- **Multiple Agents**: Runs multiple birds simultaneously to speed up the learning process
- **Fitness Tracking**: Rewards birds for surviving longer and passing through pipes

## Prerequisites

- Python 3.x
- PyGame
- NEAT-Python

## Installation

1. Clone this repository:
```bash
git clone https://github.com/yourusername/flappy-bird-ai.git
cd flappy-bird-ai
```

2. Install required dependencies:
```bash
pip install pygame neat-python
```

3. Ensure you have the necessary image files in the `imgs` directory:
   - bird1.png, bird2.png, bird3.png
   - pipe.png
   - base.png
   - bg.png

## Configuration

The project requires a NEAT configuration file (`config-feedforward.txt`) which should be in the project root directory. This file contains parameters for the neural network evolution process.

Key configuration parameters include:
- Population size
- Network architecture
- Mutation rates
- Species parameters

## Usage

Run the main script to start the AI training:

```bash
python Flappybird.py
```

The program will display:
- Current generation number
- Current score


Training continues until either:
- A bird reaches a score of 50
- 50 generations have passed

## How It Works

### Game Mechanics
- Birds automatically move forward and must navigate through gaps in pipes
- Birds can jump upward with the neural network deciding when to jump
- Colliding with pipes or going off-screen eliminates a bird

### Neural Network
Each bird is controlled by a neural network with:
- **Inputs**:
  - Bird's Y position
  - Distance to the top pipe
  - Distance to the bottom pipe
- **Output**:
  - Whether to jump (output > 0.5) or not

### Evolution Process
1. A population of random neural networks is created
2. Each network controls a bird and receives a fitness score based on performance
3. The best performers are selected to reproduce and create the next generation
4. Mutations introduce variations to improve capabilities
5. The process repeats, with each generation becoming more skilled

## Project Structure

- `main.py`: The main script containing game logic and NEAT implementation
- `Bird` class: Handles bird movement, animation, and collision detection
- `Pipe` class: Manages pipe generation, movement, and collision
- `Base` class: Handles the moving ground animation
- `main()`: Game loop function that handles bird-pipe interaction and fitness calculation
- `run()`: Sets up and runs the NEAT algorithm

## Configuration

The `config-feedforward.txt` file contains NEAT parameters. Key settings:
```ini
num_inputs = 4           # Number of network inputs
num_hidden = 0           # Number of hidden nodes
num_outputs = 1          # Number of output decisions
pop_size = 50            # Population size per generation
fitness_threshold = 100  # Target fitness to stop evolution
```


## Extending the Project

Some ideas for extending this project:
- Implement a save/load system for trained networks
- Add different game modes or obstacles
- Create a mode where humans can play against the AI
- Visualize the neural network structure during gameplay
- Optimize parameters to achieve faster learning

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- Original Flappy Bird game by Tech With Tim
- NEAT-Python library
- PyGame library


