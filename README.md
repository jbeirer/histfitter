# HistFitter

[![stable-release](https://img.shields.io/badge/Stable-v0.66.0-green)](https://gitlab.cern.ch/HistFitter/HistFitter/-/releases/v0.66.0)
[![Documentation](https://img.shields.io/badge/Documentation-blue)](https://twiki.cern.ch/twiki/bin/viewauth/AtlasProtected/SusyFitter)
[![Tutorial](https://img.shields.io/badge/Tutorial-orange)](https://twiki.cern.ch/twiki/bin/viewauth/AtlasProtected/HistFitterTutorial)

## Contact

The HistFitter Group mailing-list, for **any** of your questions: <atlas-phys-susy-histfitter@cern.ch>

## Acquire

If you're going to be using HistFitter directly as a standalone application, clone the latest stable release

```
git clone ssh://git@gitlab.cern.ch:7999/HistFitter/HistFitter.git
git checkout v0.66.0 -b v0.66.0
```

If you're using HistFitter as a submodule in a project, specify the latest stable release while adding the submodule

```
# Relative path gives nicer clones in CI if parent project on CERN's GitLab
git submodule add ../../HistFitter/HistFitter.git
cd HistFitter && git checkout v0.66.0 -b v0.66.0 && cd ..
git add HistFitter && git commit -m "Add HistFitter submodule"
```


## Setup

If you're on a machine with CVMFS you can setup using

```
source setup.sh
```

and if you're on LXPLUS and want to use AFS you can setup using

```
source setup_afs.sh
```

### Recommended Root version

The setup files automatically point at the recommended ROOT version to use.
These reside on AFS.
Have a look at the setup script if you would like to modify the ROOT version.

## Build

```
cd src
make
cd ..
```

## Directory structure

- `analysis`: Contains all files related to an analysis. E.g. `ZeroLepton/`
- `config`: Contains HistFactory schema
- `data`: Contains data text files, provided externally, used to create workspaces for analysis
- `doc`: Documentation
- `docs`: Legacy tutorial (candidate for removal)
- `examples`: Example scripts that use the libraries in `python/`
- `include`: (not needed in version control and should be removed)
- `lib`: Location shared library
- `macros`: Macros for making plots, testing the fit, ongoing work, etc
- `python`: Python base classes
- `results`: Where root files with workspaces generated by HistFactory get stored
- `scripts`: Scripts for making workspaces based on text files in data/ . Scripts for submitting batch jobs.
- `src`: Source code to make workspaces, do toys.
- `test`: pytest tests

## Contributing

To contribute to development please first [fork HistFitter](https://gitlab.cern.ch/HistFitter/HistFitter/-/forks/new) and do all of your development on a feature branch that is **not** `master`.
If you are planning on making feature changes please first [open up an Issue](https://gitlab.cern.ch/HistFitter/HistFitter/-/issues) and outline your plans so that development can be discusses with the maintainer team, streamlining the process as your MR is written.

When you make a MR, include a summary in the body of the MR of your changes that can be easily found and incorporated into Changelog for the next release.
