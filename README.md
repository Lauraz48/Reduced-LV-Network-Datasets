# Reduced Low Voltage Network Datasets

This repository releases the **Reduced ENWL_CSIRO Low Voltage Network Datasets**, a collection of structure-preserving reduced OpenDSS network models for distribution system studies.

These datasets are generated from the original ENWL_CSIRO OpenDSS networks using a structure-preserving network reduction framework. 
The reduction preserves modelling semantics and retained buses' electrical behaviour while substantially reducing model size by removing electrically superfluous buses and line segments. 
All released feeders remain directly executable in OpenDSS and are intended to support scalable power flow analysis, optimisation, hosting capacity assessment, Monte Carlo simulation, machine learning data preparation, and benchmarking of low voltage distribution networks.


## Dataset Scope

The datasets contain 512 reduced low voltage feeders across four network variants:

```text
ENWL_CSIRO_Red/
  data/
    Four-wire-red/                            128 feeders
    Three-wire-Kron-reduced_red/              128 feeders
    Three-wire-modified-phase-to-neutral_red/ 128 feeders
    Three-wire-phase-to-neutral_red/          128 feeders
```

Each feeder folder is provided as a self-contained OpenDSS case. Typical files include:
```text
Master.dss
Linecodes.dss
Lines.dss
Loads.dss
Groundings.dss
Switches.dss
Transformers.dss
```
Some files, such as `Switches.dss` or `Transformers.dss`, may be empty when the corresponding source feeder contains no enabled elements of that type.

## Reduction Description

The reduced feeders are produced using a structure-preserving reduction procedure. 
The objective is to remove electrically superfluous modelling detail while preserving explicit power system objects and the engineering interpretation of the original networks.

The reduction process includes:
- compatible series-line merging,
- inactive terminal branch removal,
- preservation of loads, sources, grounding devices, switches, transformers, linecodes, and equipment boundaries where present in the source feeder.



## Provenance

The reduced feeders are derived from the ENWL_CSIRO OpenDSS low voltage power network dataset collection (https://doi.org/10.25919/jaae-vc35).


## License and Attribution


## Citation

If these datasets are used in research, teaching, benchmarking, software development, etc., please cite the original ENWL_CSIRO data sources and the associated network reduction work that generated these reduced feeders.
