# legend-simflow-config

Repository to store all the necessary config files for running the
[LEGEND simulation workflow](https://github.com/legend-exp/legend-simflow/).

> [!NOTE]
>
> This is a metadata sub-repository. The LEGEND metadata is versioned and
> distributed centrally at
> [legend-metadata](https://github.com/legend-exp/legend-metadata).

## Structure

- `tier`: static metadata needed to build the various simflow tiers. The first
  directory level is the name of the tier (e.g. `stp`), the second is the name
  of the "setup" or "experiment" the configuration refers to. For example, below
  `stp/l200p15` we store the metadata required to run the simulations for
  LEGEND-200 in the hardware configuration used from period 15 on.

- `geom`: configuration files to build the geometries of various setups.

- `pars`: parameters of the simulation post processing (i.e. the `hit` tier). In
  this directory, we store parameters that _vary through the livetime of the
  experiment_. A classic example is the energy resolution of germanium
  detectors. The validity of the metadata is implemented through the standard
  LEGEND validity format.

## Experiments

The metadata in the `tier` directory is organized by experimental configuration,
through separate folders at the innermost level. The names of these folders are
what is called "experiment" in
[legend-simflow](https://github.com/legend-exp/legend-metadata). The experiment
labels currently supported are documented below.

### LEGEND-200

The naming convention is `l200cfgNN`, where `cfg` stands for "configuration" and
`NN` is a zero-padded integer.

- `l200cfg01`: first LEGEND-200 configuration with 142 kg of enriched germanium.
  Data taking periods p03 (start: March 2023) to p09
  ([PRL 2025](https://doi.org/10.1103/25tk-nctn).

- `l200cfg02`: same as `cfg01`, but with outer fiber barrel removed. Data taking
  period p10 (start: Feb 2024).

- `l200cfg03`: same as `cfg02`, but with nylon mini-shrouds removed in addition.
  Data taking period p11 (start: Apr 2024.

- `l200cfg04`: configuration with _only the inner barrel of the liquid argon
  instrumentation deployed_, no HPGe array. Data taking period p13, `r000` (Dec
  2024).

- `l200cfg05`: configuration with _both inner and outer barrels of the liquid
  argon instrumentation deployed_, no HPGe array. Data taking period p13, `r001`
  (Dec 2024).

- `l200cfg06`: same as `cfg04`, but with some new SiPM modules. Since new
  detectors are installed, the configuration is technically different and we
  bump the experiment label. Data taking period p13, from `r002` (start:
  Dec 2024) on.

- `l200cfg07`: 114 kg HPGe array (start: March 2025). No good data was taken
  with this configuration.

- `l200cfg08`: 99 kg HPGe array. Data taking period p14 (start: Apr 2025)

- `l200cfg09`: 138 kg HPGe array. Data taking period from p15 (start: July 2025)
  onwards.

### LEGEND-1000

The naming convention is `l1000cfgNN`, where `cfg` stands for "configuration"
and `NN` is a zero-padded integer.

- `l1000dsg01`: configuration as described in the LEGEND-1000 Conceptual Design
  Report.
