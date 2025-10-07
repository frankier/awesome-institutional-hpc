# Awesome Institutional HPC  [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)

This list is made to help you get a productive development environment as a user of institutional HPC. For an awesome list aimed at those administering HPC clusters see [Awesome HPC](https://github.com/dstdev/awesome-hpc). Sometimes making do with less tools is better for operational complexity, on the other hand these tools have generally been written to solve real problems, so it is worth at least knowing that they exist. Tools targetted at institutional HPC tend to have poor visibility since traditionally all tools are provided directly by the operator of the cluster, causing effort to be siloed. Hopefully this list helps a bit!

## Tools provided for you

Every cluster is different. Always consult your own institutions. The most common tools across instituional HPC clusters are:

* [lmod](https://lmod.readthedocs.io/en/latest/index.html) - A tool allows you to load additional software packaged as modules. Just run `module spider` to see what's available.
* [SLURM](https://slurm.schedmd.com/slurm.html) -- A job scheduler for HPC clusters which includes CLI programs you will run to interact with it
* [Apptainer](https://apptainer.org/) -- A container runtime, which supports including conversion OCI (Docker compatible) images.

## Guides

* Your own institution's guides and trainings
* [Aalto Scientitic Computing ](https://scicomp.aalto.fi/)

## Containers

<!--lint disable double-link-->
* [Apptainer](https://apptainer.org/) -- Container runtime which must be installed by your cluster administrator. It can run convert Docker images. 
* [udocker](https://github.com/indigo-dc/udocker) -- Docker compatible CLI, which does not require action from your cluster administrator, but can use Singularity as a backend if it's available.
* [singreqrun](https://github.com/frankier/singreqrun/) -- Shim to allow running programs from the host from within a Singularity container.

## Workflow managers and  distributed computing frameworks

<!--lint disable awesome-list-item-->
* [Snakemake](https://github.com/snakemake/snakemake) -- File based processing pipeline framework with workflows written on Python but additional support for CLI programs, Julia and R  with SLURM support through either:
  * Direct configuration using the `--cluster`` flag. See for example [this tutorial](https://carpentries-incubator.github.io/workflows-snakemake/09-cluster/index.html).
  * Using the [SLURM Snakemake profile](https://github.com/Snakemake-Profiles/slurm)
  * Using the KISS alternative [smk-simple-slurm](https://github.com/jdblischak/smk-simple-slurm)
  * Using [singslurm2](https://github.com/frankier/singslurm2) which allows Snakemake to spawn SLURM jobs from within a Singularity container
  * [Guide at Software Carpentries incubator](https://carpentries-incubator.github.io/workflows-snakemake/)
  * Using its DRMAA support but this is not recoomended for SLURM since its own DRMAA support is not maintained
* [Ray](https://www.ray.io/) -- Python-based distributed computing framework including tools for hyperparameter search
   * SLURM support through [yaspi](https://github.com/albanie/yaspi)
* [Nextflow](https://www.nextflow.io/) -- Workflow manager with DSL based on Groovy.
  * SLURM support though [its built-in SLURM executor](https://www.nextflow.io/docs/latest/executor.html#slurm).
* [bpipe](https://github.com/ssadedin/bpipe) Workflow manager with cluster support.
* [toil](https://toil.readthedocs.io/en/releases-3.6.x/index.html) -- Workflow manager with [batch system support](https://toil.readthedocs.io/en/releases-3.6.x/batchSystem.html).

## SLURM wrappers and libraries

* [yaspi](https://github.com/albanie/yaspi) -- A Python-based SLURM wrapper based on job arrays.
* [SEML](https://github.com/TUM-DAML/seml) -- SEML: Slurm Experiment Management Library. Integration of the sacred experiment manager and SLURM.
* [pyslurm](https://github.com/PySlurm/pyslurm) -- Python library for interfacing with SLURM.
* [slurmpy](https://github.com/brentp/slurmpy) -- Small Python library for starting SLURM jobs.
* [stubl](https://github.com/ubccr/stubl) -- Utilities for SLURM including wrappers for job launching and reporting.
* [lazyslurm](https://github.com/hill/lazyslurm) -- Intuitive terminal UI for managing slurm jobs.

## Networking

* [sshuttle](https://github.com/sshuttle/sshuttle) -- This program can help if you need to connect from outside of campus and the VPN doesn't get you where you want.
* [lsyncd](https://github.com/lsyncd/lsyncd) -- A program to sync your files to a remote server, e.g. a HPC login node. This allows a workflow where you can develop and run smoke tests locally, and then seemlessly switch to HPC for full runs.

## Fancy shell sessions

* [mosh](https://mosh.org/) -- Drop free, low latency faked SSH sessions
* [EternalTerminal](https://github.com/MisterTea/EternalTerminal) -- Another approach to drop free SSH sessions
* [xxh](https://github.com/xxh/xxh) - Bring your own shell and config to shared computing environments
* [kitty](https://sw.kovidgoyal.net/kitty/) -- Terminal supporting image display
* [Euporie](https://github.com/joouha/euporie) -- Jupyter notebooks in the terminal including support for image display with kitty
* [tmux](https://github.com/tmux/tmux) / [GNU Screen](https://www.gnu.org/software/screen/) -- Terminal multiplexers, which allow running multiple sessions and detatching and reattaching to terminal sessions
