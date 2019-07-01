Minimal SLiM recipes to measure performance under a few "large" scenarios.

## Things that will affect benchmarking:

- number of individuals
- length of the genome multiplied by recombination rate
- as time passes, more mutations accumulate and the tree sequence gets bigger, until equilibrium
- number of mutations present in the population that are under selection
- how often simplification of tree sequences occurs (the `simplificationInterval`)


## Common parameters and options:

- `L = 1e8` : genome length
- recombination rate `1e-8`
- tree sequence recording usually on
- always a nonWF model


## Recipes:

To make all of these take longer, change `NUMGENS`, the number of generations it runs for, or maybe `K`, the total population size.

- `just_reproduction.slim` : `K = 1e6` individuals for 100 time steps, no tree sequence recording, no mutations

- `neutral_mutations.slim` : `K = 1e6` individuals for 100 time steps, no tree sequence recording, neutral mutations at rate `mu = 1e-8`

- `tree_sequence.slim` : `K = 1e6` individuals for 100 time steps, tree sequence recording,
	neutral mutations at rate `mu = 1e-8`, and tree sequence simplification only twice

- `long_run.slim` : as in `tree_sequence.slim` but with `K = 1e4` for 5e4 time steps

- `geography.slim` : `K = 1e5` individuals living in a 2D region with an average density of 10 interacting neighbors,
	no mutations and no tree sequence recording, for 100 time steps

- `natural_selection.slim` : mutation rate of `mu = 1e-10`
	to mutations with selection coefficients drawn from a Normal(-1/K, 1/K) distribution, and no tree sequence recording,
	for 100 time steps

- `mosquitos.slim` : `K = 1e5` individuals for 100 time steps, with tree sequence recording,
	living in a 2D region with 20 interacting neighbors,
	and selected mutations at rate `mu = 1e-8` and selection coefficients from Normal(-1/K, 1/K)
