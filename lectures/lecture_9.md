# Lecture 9: Statistical Methods in Data Science and AI

[Lecture Slides](https://chalmers.instructure.com/courses/10918/files/998932?module_item_id=134040)

## Markov Model

### Markov Processes

#### Random Process

Is a function that varies with time and assings the outcome of a "random experiment" to each time-point, `t`. Can be any sequential structure, for example a text where a word follows another word.

#### Markov Process

Is a _random process_ where the next state only depends on the current state.

### Markov Chains

#### Markov Chain

Is a Markov process that jumps between discrete states, often also at _discrete_ time-points. Every time we jump from one tile to another in a grid, time has passed.

![markov chain](./img/markov_chain.png)

The random process, `x1, x2, x3, ...`, adopt **one** of the states `S = {s1, s2, ..., sn`, at any given time. The state `si` adopted by the process at `xt` is given by the _transition probability_ `p(si | sj)`, where `sj` is the state adopted by the process at `x[t-s]`. The initial state `x1 = si` of the Markov Process is given by the inital distribution `π = p(x1 = si)`.

#### Markos Property

`p(next state | all previous states) = p(next state | previous state)`

### Hidden Markov Model

A Hidden Markov model (HMM) can be distinguished with a _hidden random process_, such as a Markov Chain `h1, h2, ...` because it's generally not observed, and a _observed process_ that takes a random state conditioned on the state of the hidden process. This is typically a **non-Markovian**.

> $A_{m,n} =
 \begin{pmatrix}
  a_{1,1} & a_{1,2} & \cdots & a_{1,n} \\
  a_{2,1} & a_{2,2} & \cdots & a_{2,n} \\
  \vdots  & \vdots  & \ddots & \vdots  \\
  a_{m,1} & a_{m,2} & \cdots & a_{m,n}
 \end{pmatrix}$
