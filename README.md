# Exercise 9 - Recursion

## Learning goals

This exercise targets the understanding of the following subjects:
* To describe what a recursive method is and the benefits of using recursion (18.1).
* To explain how recursive method calls are handled in a call stack (18.2-18.3).
* To solve problems using recursion (18.4).
* To use an overloaded helper method to design a recursive method (18.5).

## Description

This exercise includes a couple of warmup questions and the implementation of a solution to a puzzle.
* Program your solutions using one class per problem
* Use package `aup.cs.recursion`
* Use clear class names
* Make sure to test your code before submission
* The program should be solved by setting the right class name in the build.gradle file and running it

## Warmup questions from the book

Please complete the following questions from the book. Note that using a scanner is not required and that you can run your programs by feeding them values directly.
If you do choose to use scanners, remember that you need to compile the program and then execute them separately, due to the interactiveness limitation of Gradle.
1. 18.9: (Print the characters in a string reversely) Write a recursive method that dis-plays a string reversely on the console using the following header:
`public static void reverseDisplay(String value)`
2. 18.15: (Occurrences of a specified character in a string) Rewrite Programming Exer-cise 18.10 using a helper method to pass the substring high index to the method. The helper method header is
`public static int count(String str, char a, int high)`
3. 18.25: (String permutation) Write a recursive method to print all the permutations of a string. For example, for the string abc, the permutation is abc acb bac bca cab cba
(Hint: Define the following two methods. The second is a helper method.)
```
public static void displayPermutation(String s)
public static void displayPermutation(String s1, String s2)
```
The first method simply invokes displayPermutation(" ", s). The second method uses a loop to move a character from s2 to s1 and recursively invokes it with new s1 and s2. The base case is that s2 is empty and prints s1 to the console.
Write a test program that prompts the user to enter a string and displays all its permutations.

## The subset problem

The subset sum problem is an important and classic problem in complexity theory.
Given a set of integers and a target number, your goal is to find a subset of those numbers
that sum to that target number. For example, given the numbers `{3, 7, 1, 8, -3}` and the target sum 4,
the subset `{3, 1}` sums to 4. On the other hand, if the target sum were 2,
the result is false since there is no subset that sums to 2.
The signature of this problem is `public static boolean subsetProblem(int[] arr, int target)`

## A Puzzle

You have been given a puzzle consisting of a row of squares each containing an integer,
like this: `(3) 6 4 1 3 4 2 5 3 0` and a marker denoting a cell in the puzzle, for example `0`.

At each step in the puzzle, you may move the marker the number of squares indicated by
the integer in the square denoted by the marker.
The marker may move either left or right along the row but may not move past either end.
For example, the only legal first move is to move the marker three squares to the right
because there is no room to move three spaces to the left.
The goal of the puzzle is to move the marker to the 0 at the far end of the row.
In this configuration, you can solve the puzzle by making the following set of moves: `(3) 6 4 1 3 4 2 5 3 0`

```
3 6 4 (1) 3 4 2 5 3 0

3 6 (4) 1 3 4 2 5 3 0

3 6 4 1 3 4 (2) 5 3 0

3 6 4 1 3 4 2 5 (3) 0

3 6 4 1 3 (4) 2 5 3 0

3 6 4 1 3 4 2 5 3 (0)
```

Starting position Step 1: Move right Step 2: Move left Step 3: Move right Step 4: Move right Step 5: Move left Step 6: Move right

Even though this puzzle is solvable - and indeed has more than one solution - some puzzles of this form may be impossible,
such as the following one: `(3) 1 2 3 0` .
In this puzzle, you can bounce between the two `3`s, but you cannot reach any other square.
Make sure you always manage to answer if a puzzle is solvable or not, even in the above case.
The signature of this program is `public static boolean solvePuzzle(int pos, int[] puzzle)`

### Prolog

Can you solve the puzzle using the Prolog programming language?
