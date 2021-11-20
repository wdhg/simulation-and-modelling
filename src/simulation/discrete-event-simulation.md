# Discrete-Event Simulation (DES)

Similar to discrete time, steps are made through a state transition system, but instead these steps are triggered by discrete events in continuous time. To do this, there is a single global clock that dictates the virtual time of the simulation. The triggering events are scheduled in order of time, and when an event occurs the global clock is updated to the timestamp of the event.

```

                            Virtual  ---> Direction of time
                             Time
                               |
                               V
               |---*------*----*--------*---*-------*------> ...
    Timestamp: 0   3      8    9       19  21      28

```

Events can also update the state of the simulation and queue future events.

Since events don't occur in order of generation but rather in order of their randomly sampled timestamps, discrete-event simulation is therefore an asychronous model of time. Discrete-time simulation on the other hand is a synchronous model of time as events occur in order of their generation (e.g. in a Monopoly simulation, the state gets updated as soon as the dice is rolled).

## In Practice

In practice a discrete-event simulation has:

- Continuous time (i.e. a floating-point number)
- A collection of variables (both discrete and continuous) that constitute the simulation state.
- A priority queue of events, ordered by their timestamp.
- A scheduler adds new events to the priority queue.
- A descheduler removes events from the priority queue.
- Measurement code will also be required to get output data from the simulation.

## Evolution of Time

```
    History <-- Virtual --> Future
                 Time
                   |
                   V
                Event 1           Event 2
    |--------------*-----------------*------------------> ...
                  t1                t2
                   |                 |
                   |<--------------->|
                      Δt = t2 - t1
```

In the diagram above, Event 1 at time \\( t_1 \\) schedules Event 2 at time \\( t_2 \\). To do this, an amount of time \\( \\Delta t \\) is added to \\( t_1 \\) to get \\( t_2 \\). \\( \\Delta t \\) is thus the interarrival time of the events, and so it can be modelled as a random variable. We'll need to be able to sample \\( \\Delta t \\) by sampling its distribution (more on this later).

## Discrete-Time to Discrete-Event Example

Using the Monopoly example, to change it from a discrete time simulation to a discrete event simulation we can model the move times explicitly using some random variable \\( T \\) with a specified distribution. Then at each move, we can add to the current time a sample of this distribution to progress through time (e.g. `current time + sample of T`). However if we want to simulate \\( P \\) players who roll their dice independently, we will need to think of a way to resolve the issue of updating time and shared resources (e.g. cards). This can be done using a sequence of move events in time order and controlled access to shared resources (e.g. via queueing).


