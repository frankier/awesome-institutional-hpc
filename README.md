:sungalsses: Awesome institutional HPC :sungalsses:

This list is made to help you get a comfortable . Sometimes making do with less tools is better for operational complexity, on the other hand these tools have generally been written to solve real 

# Provided for you

Every cluster is different. Always consult your own institutions. The most common tools across instituional HPC clusters are:

 * [lmod](https://lmod.readthedocs.io/en/latest/index.html) installed, which can allow you to load additional software. Just run `module spider` to see what's available.
 * [SLURM](https://slurm.schedmd.com/slurm.html) to administer the cluster queues and provide CLI programs for interacting with it
 * [Singularity](https://sylabs.io/) to allow running software from containers (including conversion from Docker)

# Guides

 * Your own institution's guides and trainings
 * [Aalto Scientitic Computing ](https://scicomp.aalto.fi/)

# Containers

 * [Singularity](https://sylabs.io/) -  Must be installed by your cluster administrator 
 * [udocker](https://github.com/indigo-dc/udocker) - Docker CLI, which does not require action from your cluster administrator, but can use Singularity as a backend
 * [singreqrun](https://github.com/frankier/singreqrun/) - Shim to allow running programs from the host from within a Singularity container

# SLURM wrappers and distributed computing frameworks

 * [yaspi](https://github.com/albanie/yaspi) - A Python-based SLURM wrapper based on job arrays
 * [Snakemake](https://github.com/snakemake/snakemake) - File based processing pipeline framework with workflows written on Python but additional support for CLI programs, Julia and R  with SLURM support through either:
   * Direct configuration: See for example 
   * Using the [SLURM Snakemake profile](https://github.com/Snakemake-Profiles/slurm)
   * Using the KISS alternative [smk-simple-slurm](https://github.com/jdblischak/smk-simple-slurm)
   * [Guide at Software Carpentries incubator](https://carpentries-incubator.github.io/workflows-snakemake/)
 * [Ray](https://www.ray.io/) - Python-based distributed computing framework including tools for hyperparamter search
   * SLURM support through [yaspi](https://github.com/albanie/yaspi)

# Fancy shell sessions

 * [mosh](https://mosh.org/) - Drop free, low latency faked SSH sessions
 * [EternalTerminal](https://github.com/MisterTea/EternalTerminal) - Another approach to drop free SSH sessions
 * [xxh](https://github.com/xxh/xxh) - Bring your own shell and config to shared computing environments
 * [kitty](https://sw.kovidgoyal.net/kitty/) - Terminal supporting image display
 * [Euporie](https://github.com/joouha/euporie) - Jupyter notebooks in the terminal including support for image display with kitty
 * [tmux](https://github.com/tmux/tmux) / [GNU Screen](https://www.gnu.org/software/screen/) - Terminal multiplexers, which allow running multiple sessions and detatching and reattaching to terminal sessions
