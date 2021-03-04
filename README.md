# Flashlite-Supernova

Supernova generates phased, whole-genome de novo assemblies from a Chromium-prepared library.

This repository contains PBS scripts that run the globally installed supernova on [University of Queensland's HPC, Flashlite](https://rcc.uq.edu.au/flashlite). 

## User guide

### 10X data

The `supernova.pbs` runs:

* `supernova run` separately for each sample to generate a whole genome de novo assembly for each.
* `supernova mkoutput` in order to generate various styles of FASTA output for your assemblies.

1. Clone this repository into your working directory on Flashlite by: 

  `git clone https://github.com/Sydney-Informatics-Hub/Flashlite-Supernova.git`

2. In `Flashlite-Supernova`, edit the variables in `supernova.pbs` including the:

* `FQ_PATH`
* `RUN_ID`
* `OUTDIR`

3. Run the script by `qsub supernova.pbs`

### TELLSeq data

You’ll need to install a local version of supernova on /30days or /90days, and then to replace the 10X barcode file with the TELLSeq provided barcode file before running the scripts.

## Benchmark metrics

| Species   | CPUs_requested | CPUs_used | CPU_percent | Mem_requested | Mem_used    | VMem_used   | CPUtime   | CPUtime_mins | Walltime_req | Walltime_used | Walltime_mins | JobFS_req | JobFS_used | Efficiency | Service_units(1*CPU_hours) | Queue | Account   | ExitStatus |
|-----------|----------------|-----------|-------------|---------------|-------------|-------------|-----------|--------------|--------------|---------------|---------------|-----------|------------|------------|----------------------------|-------|-----------|------------|
| Cockroach | 24             | 24        | 2400        | 496gb         | 158606368kb | 305991020kb | 830:26:04 | 49826.07     | 336:00:00    | 61:34:24      | 3694.4        | NA        | NA         | 0.56       | 830.43                     | Long  | qris-user | 0          |
