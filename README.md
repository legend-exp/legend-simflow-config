# legend-simflow-config

Repository to store all the necessary LEGEND-200 config files for running the
[LEGEND simulation workflow](https://github.com/legend-exp/legend-simflow/).

> [!NOTE]
>
> This is a metadata sub-repository. The LEGEND-200 metadata is versioned and
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
[legend-simflow](https://github.com/legend-exp/legend-simflow). The experiment
labels currently supported are documented below.

The naming convention is `l200cfgNN`, where `cfg` stands for "configuration" and
`NN` is a zero-padded integer. See the
[legend-pygeom-l200 documentation](https://legend-pygeom-l200.readthedocs.io/en/latest/cfg-deployments.html#supported-deployments-l200cfgnn)
for a reference of all supported configurations.

> [!NOTE]
>
> LEGEND-1000 configuration is hosted separately at
> [legend1000-metadata](https://github.com/legend-exp/legend1000-metadata).
