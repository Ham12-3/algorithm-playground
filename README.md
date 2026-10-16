# Algorithm Playground

An interactive playground where algorithms run live and animated, and you can
grab and change the data **while they run**. The algorithm reacts to your
change instead of breaking or starting over.

**Try it live: https://ham12-3.github.io/algorithm-playground/**

Everything is in a single self-contained file, `algorithm-playground.html`
(HTML, CSS and JavaScript, no libraries, no build step). Download it and open
it in any modern browser. It works with mouse and touch.

## Tabs

### Pathfinding
A 40×25 grid with draggable start and goal markers. Pick **BFS**, **Dijkstra**,
**A\*** or **D\* Lite** and watch the frontier, explored cells and final path.
While it searches you can draw walls, paint mud (cost 5) or move the markers:

- **Wall or mud added:** only the part of the search tree that went through
  that cell is dropped and regrown. The rest is kept.
- **Wall erased:** the cells around the gap are re-checked for a shortcut.
- **Goal moved:** distances from the start are still valid, so the explored
  area is kept (A\* re-aims its frontier at the new goal).
- **Start moved:** BFS, Dijkstra and A\* start a fresh search. D\* Lite searches
  backward from the goal, so it keeps its work and repairs only what changed.

### Neural Net
A small neural network written from scratch: 2 inputs, 1 or 2 tanh hidden
layers, sigmoid output, trained with Adam. It trains continuously, and the
background heatmap shows its decision boundary live. Click to add points
(shift-click for the other class), drag points to move them and watch the
boundary reshape. Presets: two blobs, circles, spiral, XOR. Sliders control
learning rate and hidden units, and a live loss chart sits in the corner.

### Sorting
50 bars sorted by **bubble**, **insertion**, **selection**, **quicksort** or
**merge sort**. Each sort is a generator that yields after every compare or
swap. Drag a bar sideways to move it, or drag its top to change its height,
mid-sort:

- **Bubble, insertion, selection:** each recalculates how much of its sorted
  region is still valid and carries on.
- **Quicksort:** redoes the current partition if your edit touches it.
- **Merge sort:** merges in place, redoes the current merge and re-sorts any
  run your edit broke.
- **Any sort:** a final check re-sorts any stretch that is still out of order.

Counters show comparisons, swaps and a 0–100% sortedness meter.

## Controls

Shared on every tab: **play/pause**, **step once**, **speed**, **reset**. A
status line at the bottom explains in plain English what the algorithm is
doing right now.

Keyboard: `Space` play/pause, `→` step, `R` reset, `1` `2` `3` switch tabs.
