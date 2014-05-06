# mazelib

#### A Python API for creating and solving mazes.  --  WORK IN PROGRESS

## The mazelib API

### Generating Mazes

    from mazelib import *

    m = Maze()
    m.generator = Prims()
    m.generate(27, 34)

### Solving Mazes

    m.solver = DFS()
    m.generate_entrances()
    m.solve()

## The Algorithms

### Maze-Generating Algorithms

#### Aldous-Broder

###### The Algorithm

1. Choose a random vertex.
2. Choose a random neighbor of the vertex and travel to it. If the neighbor has not yet been visited, add the traveled edge to the spanning tree.
3. Repeat step 2 until all vertexes have been visited.

###### Notes

This is one of the slowest maze-generating algorithms. Having said that, the end products are mazes without any major defects.

The Aldous-Broder algorithm treats the cells of a maze as a graph, and solves to find a Uniform Spanning Tree that covers that graph.

#### Binary Tree

###### The Algorithm

1. For every cell in the grid, knock down a wall either North or West.

It does not matter what order you go through all the cells in the grid. And if you are on the North edge of the grid, you will have to carve West.

###### Notes

This algorithm produces mazes with a serious flaw: the North and West borders of the maze are completely open. This makes solving the maze too easy to be fun. That is, unless the person solving the maze can't see the whole thing at one time. In which case, this algorithm is still useful.

On the positive side, this algorithm is extremely fast and very easy to implement.

#### Cellular Automaton
#### Eller's
#### Growing Tree
#### Hunt-and-Kill
#### Kruskal's
#### Prim's
#### Recursive Backtracker
#### Recursive Division
#### Sidewinder
#### Wilson's


### Maze-Soliving Algorithms

## Using the Results

For the rest of this section, let us assume we have already generated a maze:

    from mazelib import *

    m = Maze()
    m.generator = Prims()
    m.generate(27, 34)

#### Example 1: Plotting the Maze in Plain Text

It is helpful to have a low-key, fast way to print out mazes (and solutions) as you develop. I typically use this one:

    def tostr(grid):
        """Return a string representation of the maze."""
        txt = ''
        for row in grid:
            for cell in row:
                txt += '#' if cell else ' '
            txt += '\n'
    
        return txt
        
    print tostr(m.grid)

#### Example 2: Plotting the Maze with Matplotlib

#### Example 3: Displaying the Maze as CSS

#### Exmaple 4: Drawing the Maze with XKCD style
