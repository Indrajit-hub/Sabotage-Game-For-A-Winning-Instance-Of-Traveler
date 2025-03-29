# Sabotage-Game-For-A-Winning-Instance-Of-Traveler #
# Sabotage Game on K4 in NuSMV

This project models the Sabotage game on the complete graph K4 (4 vertices) using NuSMV. The game is played between a Traveler and a Demon. The Traveler aims to visit all vertices, while the Demon tries to prevent this by removing edges.

## Game Rules

1. **Traveler's Turn:** The Traveler starts at an initial vertex and can move to any adjacent vertex or stay at the current vertex in each turn.
2. **Demon's Turn:** The Demon must remove atmost one edge from the graph in each turn.  If no edges remain, the Demon does nothing.
3. **Winning Condition:** The Traveler wins if he reaches any one of
destination vertices((V4), before the Demon disconnects the graph, making it impossible for the Traveler to reach destination vertices. The Demon wins otherwise.

## NuSMV Model

The NuSMV model represents the game state, transitions, and specifications.  

* **State:** The state includes the Traveler's current location, the status of each edge (present or removed), and a flag indicating which player's turn it is.
* **Transitions:** The `next` operator defines the possible moves for the Traveler and the Demon. The Traveler can move to any connected vertex or stay put. The Demon must remove an edge if any exist.  The `TRANS` keyword is used to enforce the Demon's move constraint.
* **Specifications:**  We use CTLSPEC specifications to check for winning conditions. `CTLSPEC
    !EF (traveler = 4)` is used to find a gameplay where the traveler wins.


## Important cmd
./NuSMV -int

NuSMV > read_model -i /teamspace/studios/this_studio/svpasg/asg2/asg23.smv   ---replace with your file location

NuSMV > go

NuSMV > check_ltlspec


