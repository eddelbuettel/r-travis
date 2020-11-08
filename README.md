
## r-travis

This repository is a maintained fork of the (now deprecated) original
[r-travis](https://github.com/craigcitro/r-travis) repository by Craig Citro et al.  I was an early
contributor to this project, and quite like its design and features -- so I am keeping it around.

### Status

Maintained and used across Travis. Also useable with Github Actions, Azure Pipelines, locally using
Docker, ...

Its main advantages as are _strong portability_ as well as _ease of use_ and _customizability_. 

### Basic Usage

A minimal example of use with Travis follows:

```sh
language: c
sudo: required
dist: bionic

before_install:
  - curl -OLs https://eddelbuettel.github.io/r-travis/run.sh && chmod 0755 run.sh
  - ./run.sh bootstrap

install:
  - ./run.sh install_deps

script:
  - ./run.sh run_tests
```

This downloads the `run.sh` script, uses it to _bootstrap_ the test
environment, then installs dependencies via `install_deps` and finally runs
tests. For a realistic but real example see _e.g._ [this .travis.yml file of
package
digest](https://github.com/eddelbuettel/digest/blob/master/.travis.yml).

Numerous variations are possible: running 'test matrices' across macOS and
Linux, using BSPM for binaries (both of those [are used by
digest](https://github.com/eddelbuettel/digest/blob/master/.travis.yml),
running with several g++ versions (as used by
[RcppSimdjson](https://github.com/eddelbuettel/rcppsimdjson/blob/master/.travis.yml),
...

We also use the same approach of downloading `run.sh` and invoking it for the
different steps in with GitHub Actions (_e.g._ for
[tidyCpp](https://github.com/eddelbuettel/tidycpp/blob/master/.github/workflows/R-CMD-check.yaml)). Similarly,
Azure Pipelines can be used (as was done by a test repo on Azure).

There are also other options of use with PPAs and more---for fullest details
see the source of the shell script `run.sh`.

### More

See the [public webpage for r-travis](http://eddelbuettel.github.io/r-travis/) for more.

### Author

Dirk Eddelbuettel (for this maintained fork)

Craig Citro, Kirill Mueller, Dirk Eddelbuettel, ... (for the original r-travis)
