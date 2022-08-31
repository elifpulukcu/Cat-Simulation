# Cat-Simulation

It is a Java-based project that simulates a randomly moving cat in a world, as shown in Figure 1. The world contains walls (gray
areas), seas (blue regions), and foods (magenta cells). Cat is the orange point in Figure 1.

## Movement of a cat
A cat can move randomly in four directions: up, down, left, or right if that cell is empty, i.e., the cat cannot walk into a wall or sea. If
there is food in one of the four directions, the cat senses the food and moves/eats the food. If a cat eats food, it increases its food
variable by one. See the Cat UML diagram for the cat’s data fields in Figure 2.

<br>

<p align="center">
    <img width="1000" src="https://user-images.githubusercontent.com/110589752/187672672-8b4c723b-b7a2-4eb0-8db1-e99b83a3d944.png">
</p>

<h5 align="center">Figure 1. Left: A cat in a world, right: cat ate some of the foods</h1>

The application draws the world at each simulation time. At each time unit, the cat makes a single move. If the cat eats food,
erase the food from the world, i.e., do not draw the eaten food in magenta color anymore. Figure 1 (on the right) shows a sample
world after a few iterations where almost half of the foods are eaten.


<p align="center">
    <img width="400" src="https://user-images.githubusercontent.com/110589752/187673535-359aa5c5-9fe2-44b5-bfc3-dd36e88e9cb1.png">
</p>

<h5 align="center">Figure 2. UML diagram for the Cat class</h1>

## Format of the world input file
World is provided as text file where cells are denoted as 1=wall, 2=sea, 3=food, and 0=empty. At the beginning of the world file,
number of rows and columns are given, e.g., 40 40 as shown in the example file below.

<p align="center">
    <img width="500" src="https://user-images.githubusercontent.com/110589752/187674375-7acd475e-1605-40f6-a811-643e86228187.png">
</p>


