# 🤖 RoboMind AI: Autonomous Disaster Rescue Simulator

RoboMind AI is a browser-based simulator where a rescue robot finds the shortest safe route through a collapsed area to reach a survivor. It uses the **A\* search algorithm** to plan the path around obstacles.

**Live demo:** _add your Netlify / GitHub Pages link here_

![RoboMind AI screenshot](screenshot.png)

## The problem

After an earthquake or a building collapse, rescuers can't see which paths are blocked, and every minute matters. A rescue robot needs to find the shortest route to a survivor without wasting time exploring dead ends.

## Our solution

RoboMind AI models the disaster zone as a 10×10 grid. The user marks blocked cells as obstacles. The robot then uses A\* to calculate the shortest safe path from the start point to the rescue destination, and moves along it.

## Features

- **A\* pathfinding** with Manhattan distance as the heuristic, so the path found is always the shortest
- **Interactive obstacle map:** click or tap any cell to add or remove rubble
- **Search visualization:** cells the algorithm checked are highlighted, and the final route is drawn on top
- **Live mission dashboard:** robot position, total distance, steps remaining and cells checked
- **Two ways to run the robot:** step by step, or fully automatic with pause and resume
- **Clear failure feedback:** if obstacles block every route, the app says so instead of failing silently
- **Keyboard and screen-reader support:** every cell can be reached with Tab and toggled with Enter or Space
- **Responsive layout** that works on desktop and mobile

## How A\* works here

A\* scores each cell with `f(n) = g(n) + h(n)`:

- `g(n)` is the number of steps taken from the start to cell `n`
- `h(n)` is the estimated distance from `n` to the rescue point (Manhattan distance)

At each step the robot's planner expands the open cell with the lowest `f`. Because it is guided toward the goal, it usually checks far fewer cells than a blind search such as BFS, and the "Cells checked by A\*" counter on the dashboard shows this on every run.

## How to use

1. Open `index.html` in any modern browser. No install or build step is needed.
2. Click cells to place obstacles between the green **S** (start) and the amber **R** (rescue destination).
3. Select **Find shortest path** to calculate the route.
4. Select **Move robot one step** to advance manually, or **Auto rescue** to run the whole mission.
5. Select **Reset maze** to clear everything and start again.

## Tech stack

- HTML, CSS and vanilla JavaScript
- Single file, no frameworks or external dependencies

## Project structure

```
index.html    the full app (markup, styles and A* logic)
README.md     this file
```

## Future improvements

- Move the start and rescue points by clicking
- Multiple survivors, with the robot rescuing the nearest one first
- Larger maps and random obstacle generation
- Diagonal movement and different terrain costs
- Real sensor input from a physical robot

## Team

_Add your name and your teammates' names here._
