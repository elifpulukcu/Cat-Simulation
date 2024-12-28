# Cat-Simulation

## Overview

Cat-Simulation is a Java-based simulation program where a cat navigates a 40x40 grid world filled with obstacles, seas, and food. The program visualizes the cat's movement and tracks how much food it consumes over a specified number of steps. The world is represented as a matrix loaded from a text file, and the simulation employs the `StdDraw` library for graphical representation.

<p align="center">
    <img width="1000" src="https://user-images.githubusercontent.com/110589752/187672672-8b4c723b-b7a2-4eb0-8db1-e99b83a3d944.png">
</p>

<h5 align="center">Figure 1. Left: A cat in a world, right: cat ate some of the foods</h5>

## Features

- **World Representation**:
  - A 40x40 grid loaded from a `world.txt` file.
  - Cells represent different terrains:
    - **Empty spaces** (0): Traversable by the cat.
    - **Walls** (1): Impassable terrain.
    - **Sea** (2): Impassable terrain.
    - **Food** (3): Consumable by the cat.

- **Cat Simulation**:
  - A cat starts at a predefined position and moves randomly.
  - Consumes food if encountered and clears the cell.
  - Avoids walls and seas during movement.

- **Graphical Visualization**:
  - Grid and terrains are visually represented using colors:
    - Walls: Light gray.
    - Sea: Light blue.
    - Food: Magenta.
  - Cat's movement is animated, leaving a trail behind.

- **Customizable Steps**:
  - The number of simulation steps can be adjusted to observe the cat's behavior over time.

- **Output**:
  - Saves a snapshot of the simulation as an image (`output_figure.png`).

## Implementation Details

### Classes

#### `Cat`
- Represents the cat's position, color, and food consumption count.
- Key methods:
  - `draw(String direction)`: Moves and redraws the cat based on the specified direction.
  - `getX()`, `getY()`: Get the cat's current coordinates.
  - `setFoodCount(int foodCount)`: Updates the food consumption count.
 
<p align="center">
    <img width="400" src="https://user-images.githubusercontent.com/110589752/187673535-359aa5c5-9fe2-44b5-bfc3-dd36e88e9cb1.png">
</p>

<h5 align="center">Figure 2. UML diagram for the Cat class</h5>

#### `Main`
- Handles:
  - Loading the world matrix from `world.txt`.
  - Visualizing the world using `StdDraw`.
  - Managing the cat's movement and interaction with the world.

### World File (`world.txt`)
- The `world.txt` file represents the 40x40 grid as a matrix with values separated by semicolons (`;`).
- Example:
  ```
  0;0;0;1;1;2;3;0;0;0;...
  0;1;0;1;2;3;0;0;0;1;...
  ...
  ```
  <p align="center">
    <img width="500" src="https://user-images.githubusercontent.com/110589752/187674375-7acd475e-1605-40f6-a811-643e86228187.png">
</p>


### Movement Logic
- The cat moves randomly in one of four directions:
  - **Up**, **Down**, **Left**, or **Right**.
- Movement conditions:
  - The cat avoids walls and seas.
  - The cat eats food when encountered, increments its food counter, and clears the cell.

### Visualization
- The grid and terrains are drawn using `StdDraw`:
  - Each cell is represented as a square.
  - The cat is drawn as a circle in orange.
  - Movement is animated with color updates for the trail.

## Prerequisites

- **Java Development Kit (JDK)**: Version 8 or higher.
- **StdDraw Library**: Ensure the `StdDraw` graphics library is included in the project. You can download it from [Princeton StdDraw Library](https://introcs.cs.princeton.edu/java/stdlib/).

## Getting Started

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/elifpulukcu/Cat-Simulation.git
   ```

2. **Navigate to the Project Directory**:
   ```bash
   cd Cat-Simulation
   ```

3. **Compile the Java Files**:
   ```bash
   javac *.java
   ```

4. **Run the Application**:
   ```bash
   java Main
   ```

5. **Output**:
   - A graphical simulation window will appear showing the cat's movement in the grid world.
   - The program generates an output image file: `output_figure.png`.

## Customization

- **Number of Steps**:
  - Change the `stepCount` variable in the `Main` class to adjust the simulation duration.
  - Example:
    ```java
    int stepCount = 10000; // Simulates 10,000 steps
    ```

- **World File**:
  - Modify the `world.txt` file to customize the grid's layout and initial content.
  - Ensure the file adheres to the 40x40 matrix format with values separated by semicolons.

- **Cat's Initial Position**:
  - Modify the cat's starting coordinates in the `Main` class:
    ```java
    Cat cat = new Cat(30, 20, StdDraw.ORANGE); // Change (30, 20) to desired coordinates
    ```

## Limitations

- The simulation is restricted to a 40x40 grid.
- Movement decisions are entirely random and do not consider optimization or pathfinding.
- The cat cannot revisit cells where food has already been consumed.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

## Author

Developed by [Elif Pulukçu](https://github.com/elifpulukcu).



