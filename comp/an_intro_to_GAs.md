# An introduction to Genetic Algorithms, Melanie Mitchell, 5th printing 1999

## Chapter 1: Genetic Algorithms: An overview

### Overview

- Human desire for control, science and prediction.
- Electronic computers- a revolution.
- Computer science combined with biology and psychology. Artificial intelligence and artificial life. Neural Networks, Machine Learning, Evolutionary Computation (GAs being the most prominent example of the latter).

### 1.1 A brief history of evolutionary computation

- 50s & 60s, evolutionary systems used for optimisation problems. Idea to evolve a population of candidate solutions using variation and selection.

- 60s, Rechenberg (1965, 1973) introduced "evolution strategies" to optimise real-valued parameters used for e.g. airfoils. Idea further developed by Schwefel (1975, 1977).

- Fogel, Owens and Walsh (1966) developed "evolutionary programming", where candidate solutions were presented as FSMs which were evolved by mutating their transition diagrams.

- Many other ideas were explored, and biologists used computers to simulate evolution for controlled experiments.

- GAs were invented by John Holland in the 1960s and developed until the 70s. In contrast with evolution stategies and evolutionary programming which were designed to solve specific problems, Hollan's original goal was to formally study the phenomenon of adaptation as it occurs in nature and to develop ways of modelling it with computers. Holland's *Adaptation in Natural and Artificial Systems*(1975) presents the genetic algorithm as an abstraction of biological evolution.

- GA is moving from one population of *chromosomes* (e.g. string of bits, 0/1) to a new population by  a kind of *natural selection*, together with the genitics-inspired operators of *crossover*, *mutation* and *inversion*. Each chromosome consists of *genes* (bits), each gene being an instance of a particular *allele*(i.e. a 0 or a 1).
    - Crossover exchanges subparts of two chromosomes (mimicking biological recombination between two single-chromosome "haploid" organisms)
    - Mutation randomly changes allele values of the chromosome's genes.
    - Inversion reverses the order of a continuous section of the chromosome.
  
  ![cell-nucleus-chromosome-DNA-gene.png](https://raw.githubusercontent.com/cristiean/images/mark-text/2020/04/11-22-19-22-cell-nucleus-chromosome-DNA-gene.png?token=AF25T2EX2QGIETZ7W7FTOGS6SI2JQ)

-  Holland's population-based algorithm with crossover, inversion and mutation was a major innovation
    - Rechenberg's initial evolution strategies started with two individuals: a parent and its offspring (a mutated version of the parent)
    - Evolutionary programming also only used mutation for variation.

- Holland's was also the first attempt to formalise computational evolution, the theory being based on the notion of [*schemas*](https://en.wikipedia.org/wiki/Schema_(genetic_algorithms))

- Nowadays, evolutionary computation methods have less defined boundaries. GAs, evolution strategies, evilutionary programming, all under the same "family" of GAs.

### 1.2 The appeal of evolution
- Evolution as inspiration:
    - Parallel computation
    - Intelligent choice of next potential solution to try
- Computational problems require computer programs to be:
    - *Adaptive* to the environment (e.g. robot control)
    - *New and original*
    - Potentially *complex*
        - e.g. Connectionism and Evolutionary systems display complex behaviour (pattern recognition, optimisation) from simple "bottom-up" rules (neural thresholding and activation, natural selection with variation) as opposed to rule-based systems (expert systems)
- Evolution solves an ever-changing search problem: Finding the fittest individuals (survival and reproduction) by gene mutation. Also, the computation is done in parallel.

### 1.3 Biological terminology
- Organisms contain *cells*
    - Each cell contains the same set of one or more *chromosomes* (strings of DNA) that serve as a "blueprint" for the organism
    - Chromosomes can be conceptually divided into *genes*- each encoding a particular protein
    - Each gene can be thought of as giving rise to a phenotypical trait. Each possible "setting" for a trait is called an *allele*
    - Each gene is located at a particular *locus* on the chromosome

- Many organisms have multiple chromosomes within a cell
    - The entire collection of chromosomes is called a *genome*
    - The *genotype* is the collection of genes contained by a genome
    - The genotype, under particular conditions, gives rise to the *phenotype*- its physical characteristics

- *Diploid* organisms have chromosomes arrayed in pairs. *Haploid* have unpaired chromosomes.
    - In nature, most sexually reproducing are diploid (including humans, who each have 23 pairs of chromosomes in each somatic i.e. non-germ cell in the body)
    - During sexual reproduction, *recombination (or crossover)* occurs:
        - In each parent, genes are exchanged between each pair of chromosomes to form a *gamete* (a single chromosome)
        - Gametes form the two parents pair up to create a full set of diploid chromosomes
        - In haploid sexual reproduction, genes are exchanged between the two parents' single-strand chromosomes
    - Offspring are subject to *mutation*, in which single nucleotides (elementary bits of DNA) are changed from parrent to offspring (often from copying errors)
    - The *fitness* of an organism is typically defined as the probability that the organism will live to reproduce (*viability*) or as a function of the number of offspring the organism will have (*fertility*)

- In GAs:
    - Chromosomes are candidate solutions to a problem, encoded as a bit string
    - Genes are either single bits of short blocks of adjacent bits
    - Alleles are 0 or 1, or more for larger alphabets
    - Crossover is the exchanve of genetic material between two singlechromosome haploid parents
    - Mutation is a bit flip at a random location. For larger alphabets, a random change at a random locus.

### 1.4 Search spaces and fitness landscapes
- Search space: A collection of all candidate solutions.
- Fitness landscape: A representation of candidate solutions and their fitness in an $n+1$ dimensions, for genotypes of length $n$
- Neighbouring candidates are assumed to have similar fitnesses.

### 1.5 Elements of GAs
- GAs are a term used for most evolutionary computation methods nowadays. They have at least the following in common:
    - Population of chromosomes
    - Slection according to fitness
    - Crossover to produce new offspring
    - Random mutation of offspring
    - NOTE: Inversion is rarely used and its advantages, if any, are not well established.
- GAs often require a fitness function, mapping chromosomes to a score (how well does it solve the problem).
- Examples of fitness functions:
    - Function optimisation $f(y)=y+|\sin(32y)|$, $0\leqy\leq\pi$
    - Finding a sequence of 50 amino-acids that will fold to a desired 3D protein structure. Candidates could be encoded as a 50-letter string where each letter represents one of the 20 possible amino acids.
- GA Operators:
    - **Selection**: the fitter the chromosome, the more it is likely to be selected to reproduce
    - **Crossover**: randomly chooses a locus and switches the subsequence from that point on between two chromosomes.
    - **Mutation**: can randomly flip some bits in the chromosome with usually a very small probability

### 1.6 A simple GA
NOTE: Skipped

### 1.7 GAs and Traditional search methods
(At least) three meanings of "search":
- **Search for data** in a collection of stored records
    - e.g. solution: binary search
- **Search for path to goal** (goal representation is known)
    - e.g. problem: 8-puzzle
    - e.g. solution: DFS, A\*, branch-and-bound
- **Search for solutions** (unknown solutions)
    - subsumes search for path to goals
    - e.g. solutions: GAs, hill climbing, simulated annealing, tabu search, steepest-ascent hill climbing

- General methods are called "weak methods".
- Methods designed for particular problems are called "strong methods".

### 1.9 Two brief examples
- Prisoners' Dillema
- Hosts and Parasites: Using GAs to evolve sorting networks. NOTE: Skipped

### 1.10 How do GAs work?
- Traditional theory of GAs (Holland 1975) assumes that, in general, GAs work by discovering, emphasizing, and recombining good "building blocks" of solutions in a highly parallel fashion. He introduces the notion of *schemas* to formalise "building blocks".
- NOTE: skimmed through.
- Implicit parallelism by emphasising above-average-fitness schemas
- However, mutation ensures variation
