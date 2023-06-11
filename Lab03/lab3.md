### Exercise 1

Testing ES with strategy=None:
 - What happens if you make $\lambda$ smaller e.g. $\lambda=\mu$?

By reducing $\lambda$ we obtain worse and worse results, this is probably due to the fact that having a higher number of offsprings permits better exploration of the solution space.

| $\lambda$ | Best fitness |
|-----------|--------------|
| 40        | 145.00       |
| 100       | 103.80       |
| 200       | 67.03        |

 - What happens if you increase the mixing number $\rho$?

By increasing $\rho$ (>1) we introduce higher and higher selection pressure, that means that using a high $\rho$ tends to worsen the fitness, but keeping low selection pressure make the fitness value go lower.

| $\rho$ | Best fitness |
|-----------|--------------|
| 1         | 103.80       |
| 2         | 77.02        |
| 5         | 143.64       |

 - Does this confirm or contradict the conclusions you drew in the first module?

 It confirms what I drew in the first module.


 ### Exercise 2

 - How does the self-adaptation strategy influence performance on this problem?

Both GLOBAL and INDIVIDUAL strategies lower the resulting fitness, in particular the INDIVIDUAL strategy seems to produce consistently better best offsprings, but on average the fitnesses are similar to GLOBAL's.

 - Does what you see here confirm what you suspected from the previous exercise?

Yes.

 - How do the values of $\mu$, $\rho$, and $\lambda$ influence the performance given a particular self-adaptation strategy and other parameters?

By increasing $\mu$ (from 20 to 50) the GLOBAL strategy gave very good results wrt. other strategies. Increasing $\lambda$, but still keeping the right balance between $\lambda$ and number of generations, GLOBAL seems to be again the best strategy. By increasing $\rho$ both GLOBAL and INDIVIDUAL produce better results.

 - Can you come up with any rules of thumb for choosing these parameters?

I would say that indipendently from ($\lambda \times No.Gen.$) it is always good to have a reasonably large initial population size and to keep $\rho$ > 1.

 - Can you find a choice of parameters that works properly across several problems?

The combination: $\mu$ = 50, $\rho$ = 2, $\lambda$ = 100, no.gen = 100, seems to find good minima to all of the three problems (Sphere, Rosenbrock, Rastrigin). The Rastrigin problem, as expected is the most difficult one.

### Exercise 3

I compared CMA-ES with ES on the Rastrigin problem.

 - Can CMA-ES find optima to different problems with fewer function evaluations?

CMA-ES seems to be converging to its best solution after a higher number of function evaluations with respect to standard ES.

 - How do these differences change with different pop. sizes and problem dimensions?

By increasing the pop. sizes convergence time increases, but results are fairly similar.

 - In what ways are certain strategies more biologically plausible than others?

I believe that Evolving strategies involving correlated mutations are the most biologically plausible, since they use individual step-sizes and pair-wise rotations.

 - Describe what reasons may contribute to better performance of CMA-ES and what can be the conditions when CMA-ES is not better than a basic ES.

CMA-ES avoids statistially "useless" parts of the exploration space, so offsprings are solely conditioned by the ones that score the best. In simpler problems (such as the Sphere problem), CMA-ES and standard ES perform the same.
