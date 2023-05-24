# Complexity

[TOC]

## What is Complexity in Computation?

Complexity is a field of study about resources (time and memory) used by the algorithm.



## Polynomial / Exponential Time

The complexity class of all problems that can be solved in **polynomial** time on a **deterministic** RAM.

In the case of **deterministic RAM**, the algorithm can take **polynomial** (P) or **exponential**  (EXPTIME) time to find a solution.



### Comparison of runtimes

![](https://thecodingbay.com/wp-content/uploads/2022/04/Complexities-Graph1.png)



---



## Non-Determinism 

- ### In Algorithm

**A non-deterministic algorithm** is an algorithm that can provide different outputs on different runs even for the same input.

In the case of **non-deterministic RAM**, the algorithm can take **polynomial** (NP) or **exponential** (NEXPTIME).

- ###  in Computation

In a deterministic machine, from a state, there will be only one next state (Deterministic Finite Automata). 

In the case of a **Non-Deterministic machine**, from a state, there can be **multiple next states** (Non-Deterministic Automata).

**Non-determinism** can be viewed as a kind of parallel computation wherein the multiple independent *"processes"* or *"threads"* can be running **concurrently**.

Note that there is **NO** *non-deterministic* RAM/machine that exists. It is just a **theoretical** concept.

- #### Comparison between Deterministic and Non-Deterministic Computation

![](https://upload.wikimedia.org/wikipedia/commons/1/16/Difference_between_deterministic_and_Nondeterministic.svg)

---



## NP Problems

This is a complexity class of all problems that can be solved in **polynomial** time on a **non-deterministic** RAM.

In general, **NP** problems are **hard** problems. For the NP problems, **finding a solution** is harder but can **verify** easily (ie., in **polynomial time**). 

For example - Sudoku

### How to solve an NP problem in a Deterministic RAM machine?

You can **simulate the NP ** (Non-deterministic) problem in a deterministic RAM machine with the worst **exponential** time by walking through different choices of transition. 

The reason is that we have to explore all possible paths one by one and accept the solution. So, to simulate a non-deterministic problem in a deterministic RAM machine, we need a lot of memory and time resources.

---



## P Versus NP

- **P = NP**

  If P = NP then the problem you can **verify** in polynomial time, you can **solve** it in polynomial time as well. But practically that is not the case.

- **P != NP**

  All scientists believe P != NP because, for all NP problems, we can **verify** in polynomial time, and solving it takes **exponential** time (as it has to explore all possible paths/combinations).



---

## NP-Hard Problems

They are a class of problems, **"as hard as" every other problem in NP**.

So, the question is - how to quantify a problem hard?

Here comes a notion called **reduction**. If you can take a known NP-hard problem and reduce them to some **NP problem in polynomial time** (**reduction has to be in polynomial time**), then you quantify that problem as **NP-hard**. 

That is, you have established some kind of **relationship between the problems**. If either one is solved, the solution can be obtained for the other.

In conclusion, **NP-Hard** problems are **hard** to solve. Even if you solve it, it's **hard** to verify.

## NP-Complete Problems

They are a class of problems, where that is in **NP-hard and in NP**.

**So, NP-Complete is at the intersection of NP-Hard and NP**.

In conclusion, **NP-Complete** problems are **hard** to solve, **easy** to verify, and can be reduced to any other **NP-Complete** problem.



## Relationship between P, NP, NP-Complete, and NP-Hard



![](https://www.baeldung.com/wp-content/uploads/sites/4/2020/03/P-NP-NP_Hard-NP-Complete-1-1.png)





## Important Complexity Classes

![](https://discretegames.github.io/assets/complexities/complexity_classes.png)

## How to Solve Hard Problems?

We may not be able to find the **optimal** solution. But the objective is to find out the **near-optimal** solution.

Typically, the hard problems take **exponential** time (for ex: $$2^n$$, n being input size), which is not acceptable. By different techniques, if we can change  the *base* of the exponent for the run time, may yield better results (for ex: $$1.7^n$$).

For the **harder** problems, the size of the input (*n*) is not the only problem; the structure of the input (k) also matters. 

Following are some of the approaches to solving NP-Complete or NP-Hard problems.

- With Performace Guarantee

  1. **Optimized Search Trees and pre-processing.**

     Avoid the exhaustive search space by optimizing the tree. 

     The **pre-processing** here is to trim the input (aka clean the input space), which would result in **reduced search space**. Also, note that the *pre-processing* should be in *polynomial* time and that should not affect the *solution*.

  2. **Approximation Algorithms**

     They provide mathematical proof certifying the quality of the returned solution in the worst case.

     The objective is to find the **near-optimal** solution.

     - Constant Factor Approximation

     - Polynomial Time Approximation Scheme (PTAS)

  3. **Randomized Algorithms**

     Uses a **random** number in the algorithm. It employs some degree of *randomness* as part of its logic or procedure. It usually uses a *pseudo-random number generator*, which is a **deterministic**.

      * Las Vegas algorithm

      * Monte Carlo algorithm

        

- No Performace Guarantees.

  - Heuristics Algorithm: They reasonably find a good solution on some inputs but provide no clear indication at the outset of why they succeed or fail.
    - Genetic Algorithm
    - Simulated Annealing
    - Local Search
  - Metaheuristic

## Resources

* [Blog: P - NP - NP-Complete - NP-Hard](https://www.baeldung.com/cs/p-np-np-complete-np-hard)
* [MIT Open Courseware - Algorithm Lower Bounds, Course # 6.890](https://ocw.mit.edu/courses/6-890-algorithmic-lower-bounds-fun-with-hardness-proofs-fall-2014/video_galleries/lecture-videos/)
* [Udacity Course - Theoretical Computer Science cs313](https://www.udacity.com/course/intro-to-theoretical-computer-science--cs313)
* Book: Computers and Intractability, Michael Garey and David Johnson
* Book: Games, Puzzles and Computation, Robert Hearn and Erik Demaine

