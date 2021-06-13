# (A New Golden Age for Computer Architecture)[https://cacm.acm.org/magazines/2019/2/234352-a-new-golden-age-for-computer-architecture/fulltext]
By John L. Hennessy, David A. Patterson

- Software talks to hardware through a vocabulary called Instruction Set Architecture (ISA)
- Controlling data paths with control stores (2d array, columns- control lines, rows- microinstructions). Writing microinstructions- microprogramming.
    - NOTE: Would like to understand these control stores better.
- The marketplace is rarely patient.
- Early 1980s, Complex Instruction Set Computers (CISC). Unix demonstrating that operating systems could use high-level languages, the question became: "What instructions could computers generate" instead of "What assembly language would programmers use?".
- 20% of VAX instructions need 60% of the microcode and represent only 0.2% of the execution time.
- Less complex ISAs for microprocessors- Reduced Instruction Set Computer (RISC).
    - First, RISC instructions were as simple as microinstructions so there was no need for a microcontroller. 
    - Second, the memory previously used by microcontrollers was repurposed for RISC instruction caches (a cache is a small, fast memory that buffers recently executed instructions, as such instructions are likely to be reused soon)
    - Third, register allocators based on Chaitin's graph-coloring scheme made it much easier for compilers to efficiently use registers.
- *Computer Architecture: A quantitative approach* set to compare architectures based on quantitative measurements as opposed to architects' intuition and experience.
- Veri Long Instruction Word (VLIW) and Explicitly Parallel Instruction Computer (EPIC) shifted more of the work to the compiler. VLIW and EPIC were meant to supersede RISC. Itanium failed to live up to this promise as the compilers needed were "impossible to write" as Donad Knuth later noted.

## RISC vs CISC in the PC and Post-PC eras
- PC era x86 peaked in 2011.
- iPhone 2007 marked the beginning of the post-PC era, with RISC processors from ARM chosen for smaller die size and increased energy efficiency. The Internet of Things further accentuated the need for performance and energy efficiency.
- Today, 99% of 32-bit and 64-bit processors are RISC.


- Program branch prediction is non-trivial for general-purpose programs. While it afforded performance improvements, these cost energy. Therefore, the architects needed to find a different approach to achieve performance improvements. Thus the multicore era was born.
- Amdahl's Law, stating that the speedup from a parallel computer is limited by the portion of computation that is limited, shows that, for example, when 1% of the computation is serial, the speedup for a 64-processor config is about 35x. Unfortunately, the power needed is proportional to 64 processors, so approximately 45% of the energy is wasted.
- Amdahl's and Denner's Laws means that the more cores there are, the more energy is being used, and the more heat needs dissipated. Multicore processors are limited by the Thermal Dissipation Power (TDP). The energy that goes into the processors goes out as heat.
- The limit of TDP led to the era of "dark silicon"- processors slowing down the clock rate and turning off idle cores to prevent overheating.
- An era without Dennard scaling, along with reduced Moore's Law and Amdahl's Law in full effect means only a slight performance improvement year over year (a few percents). This requires a new approach that uses the current architectures much more efficiently.
- Security used to be embeded in the architectural process of a processor. With PCs, this has not been the case anymore. Security needs to be a first-class design concern once again.

- High-level languages are inefficient. For example, Python matrix-multiplication can be improved 62806-fold. (Liserson et al)
- Domain-specific-architectures (DSA). E.g. GPUs, neural network processors, etc.
    - DSA can exploit more efficient parallelism for the specific domain.
    - Make more effective use of memory hierarchy (cache levels, off-chip DRAM). This can be done by the programmers and the compilers much better in DSLs than dynamic caching. Caches have two main disadvantages:
        - Caches do not work well when datasets are very large
        - Caches wodk well when locality is very high which, by definition, means that the cache is idle most of the time
    - DSAs can use less precision when adequate.
- Domain-specific Languages (DSL) can target high-level operations to the architecture explicitly (TensorFlow, Matlab, etc.) as opposed to Python, Java, C or Fortran.


## Summary
- Vertically integrated design teams that understand applications, domain-specific languages and related compiler technology, computer architecture and organisation, and the underlying implementation technology will be advantaged. This, as opposed to the horisontal organisation the industry currently is in.
- This opportunity has already led to a surge of architecture innovation:
    - GPUs - use many cores, each with large register files, many hardware threads, and caches (NVIDIA)
    - TPUs - rely on two-dimensional systolic multipliers and software-controlled on-chip memories (GOOGLE)
    - FPGAs - (Field Programmable Gate Arrays) tailors Neural Network applications (MICROSOFT)
    - CPUs - many cores, advanced multi-level caches ... (INTEL)

## Open architecture
... might drive more innovation
- RISC-V
- NVDLA (NVIDIA Deep Learning Accelerator)
- 
