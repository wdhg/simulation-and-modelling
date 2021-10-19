# The Response Time Law

If a closed system has a fixed population of `N` users (or customers, packets, jobs, etc) working in "think/compute" mode (i.e. they have a "think time" `Z` between the completion of a job and the submission of the next) then this is a special case of Little's Law:

```

  N users with think time Z

           +-()-+
           + () +
    *------+ .. +<-----*
    |      +-()-+      |
    |                  |
    |                  |
    |                  |
    *---->(System)-----*

       Response time R

```

The average total time for each cycle is `R + Z` so from Little's Law: `N = X * (R + Z)` or rearranged as `R = N/X - Z`. Note this **only** applies for the entire closed system, any subsystem will still obey Little's Law.

