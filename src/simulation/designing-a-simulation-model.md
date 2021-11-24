# Designing a Simulation Model

This section will run through designing a simulation model step-by-step using Monopoly as an example. Note that a lot of the examples will be dependent on the simulation implementation.

## 1. Identify the entities

The most important entities would the player pieces. Depending on how the simulation is implemented, this could also include other things such as the board tiles (properties, jail, etc) and their cards.

## 2. Identify the model states

In practice, these would be the state variables of the program. In terms of the example, these could include:

- The positions of player pieces.
- The amount of money each player has.
- Who owns which properties.
- The buildings on each tile.

## 3. Identify the types of events

Events are what trigger state transitions, such as:

- Moving from dice rolls.
- Chance and community chest cards.
- Go to jail tile.

Note that some events can be parameterisable.

## 4. For each event...

### i. Specify how the event changes the current state of the system

- Rolling the dice will move a pieces position.
- A piece that lands on a property owned by another player will cause them to pay rent.
- Picking a card could cause a variety of other changes.

### ii. Identify which new events need to be scheduled

- Rolling the dice will queue another dice roll for the next player.

## 5. Write code to perform measurements

- Counting the number of times each property is landed on.
- Counting how much rent is collected at each property.

## 6. Output the measurement results at the end of the simulation.

Could be in the form of raw data and/or graphs.
