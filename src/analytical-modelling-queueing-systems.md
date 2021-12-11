# Analytical Modelling: Queueing Systems

**Analytical methods** are used to analyze models mathematically and probabilistically.

There are three main approaches/methods to analyze a system:

1. Measurement approach.
2. Simulation approach.
3. Analytical modelling.

### Measurement Approach

Pros:

- Simple to do.
- Collected data is the ground truth (not relying on any assumptions).
- No knowledge of the system is required, and can be applied to any system.

Cons:

- Typically slow.
- Rare events may not occur during the tests.
- Takes some effort to automate the process.
- Collected results can be affected by "noise".

### Simulation Approach

Pros:

- Easy to learn.
- Easy to produce/reproduce rare events and assess their impact.
- Fast enough for repeated evaluations (can typically run in minutes to hours).

Cons:

- Modelling skills are require
- Knowledge about the system is required to model it.
- Simulation software can have (many) bugs.

### Analytical Modelling

Pros:

- Fast (typically within seconds to minutes).
- Helpful for optimisation-based search.
- Helpful for machine learning and probabilistic inference.
- Is typically the main method used for formally proving properties of an algorithm or of system behavior.

Cons:

- Strong modelling skills are required.
- Knowledge about the system is required to model it.
- Works better on simpler systems (e.g. single resources) compared to complex systems.

Measurement, simulation, and analytical methods are complementary and should be used together: they aren't competing alternatives.
