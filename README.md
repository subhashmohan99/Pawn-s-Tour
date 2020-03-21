#Pawn's Tour

## Table of Contents

- [Objective](#objective)
- [Installation](#installation)
- [Run Program](#run-program)
- [Solution](#solution)
- [Testing](#testing)
- [Built With](#built-with)
- [Sources](#sources)

## Objective
* Write a program that finds at least one path for the pawn to visit all tiles on the board following the below rules, starting from any tile.
  * A pawn can move on 10x10 chequerboard horizontally, vertically and diagonally by these rules:
    * 3 tiles moving North (N), West (W), South (S) and East (E)
    * 2 tiles moving NE, SE, SW and NW
    * Moves are only allowed if the ending tile exists on the board
    * Starting from initial position, the pawn can visit each cell only once

## Installation

These Instructions assume that you already have [Ruby](https://www.ruby-lang.org/en/documentation/installation/) and the [Bundler Gem](http://bundler.io/) installed.

First you need to download and uncompress the code to a folder. I'm going to use my Desktop.

```bash
$ cd ~/Desktop
$ tar -xvf mohan-subhash_platform-Assignment-1.tgz
```

Next we need to jump into the folder we just uncompressed:

```bash
$ cd mohan-subhash_platform-Assignment-1
```

Now we need to install all of the dependencies:

```bash
$ bundle install
```

## Run Program

Navigate to the project folder if not already there.

```bash
$ cd ~/Desktop/mohan-subhash_platform-Assignment-1
```

Now we can run the program.

To display the pawn tour path for default 10x10 chequerboard with (x0, y0) run:

```bash
$ ruby pawn_tour.rb 
```

To provide an option other than default values:

For example: To display the pawn tour path for 5x5 chequerboard with (x2, y2) run:

```bash
$ ruby pawn_tour.rb -n 5 -x 2 -y 2
```

If you want assistance through the Terminal:

```bash
$ ruby pawn_tour.rb -h
# Welcome to the Pawn's Tour Path Help Menu!
# Use '-n' to set the n x n grid. Default value is 10.
# Use '-x' to set the starting x position. Default value is 0.
# Use '-y' to set the starting y position. Default value is 0.
# Please maintain the order while passing the arguments as shown in the below example.
# Example: ruby pawn_tour.rb -n 5 -x 1 -y 1
```

## Solution:

The problem is solved using H C Warnsdorff's technique which does the following:

1. Start from any tile and mark it as visited.
2. To decide next tile in path, look at all possible unmarked tiles based on moving rules.
3. Rank each possibility by the number of next moves from that tile.
4. Move to any tile with the lowest rank.
5. Mark chosen tile to pawn's tour path and repeat the process from last chosen tile.

## Testing

Open your Terminal and navigate to your project folder.

```bash
$ cd ~/Desktop/mohan-subhash_platform-Assignment-1
```

Run the testing suite:

```bash
$ rspec spec --format documentation
```

## Built With

- [Ruby](https://www.ruby-lang.org/en/)
- [Bundler Gem](http://bundler.io/)
- [RSpec Gem](http://rspec.info/)

## Sources:

* [Knight's Tour - Warnsdorff's rule](https://en.wikipedia.org/wiki/Knight%27s_tour)
