# AGENTS.md

A metadata sub-repository of
[legend-metadata](https://github.com/legend-exp/legend-metadata), holding the
configuration files that drive the
[legend-simflow](https://github.com/legend-exp/legend-simflow) LEGEND
simulations production (the Simflow), as YAML. This is data, not code.

## Conventions

- The format of the metadata is defined in the
  [LEGEND Data Format Specification](https://legend-exp.github.io/legend-data-format-specs/dev/metadata/);
- The metadata is always organized by "experiment", see naming convention in the
  `README.md`;
- Each experiment has a starting validity timestamp range, and this is usually
  the same across the respective metadata;
- Make sure the simulation identifiers (`simid`\ s) are always defined in the
  `stp` tier config;

## Files

The following files configure:

- `logging.yaml`: Simflow logging (Python `logging` module);
- `geom/`: simulated experimental geometry, as constructed by
  `legend-pygeom-l200` and `legend-pygeom-l1000` Python packages;
- `pars/<exp>/`: parameters of the simulation;
  - `geds/`: parameters for HPGe detectors;
    - `aoemeanmod/`: parameters of the energy dependence of the mean A/E;
    - `aoeresmod/`: parameters of the energy dependence of the A/E resolution;
    - `currmod/`: parameters of the current signal model for the
      single-template-based PSD simulation;
    - `elecmod/`: parameters of the electronics chain model;
    - `opv/`: operational voltages of the detectors;
    - `psdcuts/`: cut values for the PSD classifiers;
    - `skip/`: detectors for which PSD modeling should be skipped (e.g. because
      it's not possible to simulate them);
    - `ssd/`: parameters for the `SolidStateDetector.jl` pulse-shape simulations
      (static);
    - `superpulses/`: settings for the construction of average waveforms from
      data;
- `tier/<exp>/`: settings for each tier in the Simflow;

## Checks

Always run pre-commit before committing; let it auto-fix what it can and fix any
remaining errors it reports:

```console
$ pre-commit install
$ pre-commit run --all-files
```

Some of these are custom checks on this repository's format (notably
`validate-validity`), run by pre-commit and implemented in
[pylegendmeta](https://github.com/legend-exp/pylegendmeta).
