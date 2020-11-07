
## r-travis

This repository is a maintained fork of the (now deprecated) original
[r-travis](https://github.com/craigcitro/r-travis) repository by Craig Citro et al.  I was an early
contributor to this project, and quite like its design and features -- so I am keeping it around.

### Status

Maintained and used across Travis. Also useable with Github Actions, Azure Pipelines, locally using
Docker, ...

Its main advantages as are _strong partability_ as well as _ease of use_ and _customizability_. 

### Usage

In the continuous integration setup, down the script `run.sh` and use its key steps `bootstrap`,
followed by either `install_all` or `install_deps` which prepare the test, and then just `run_tests`
(and optionally `dump_logs` and maybe `coverage`.  See [this simple .travis.yml of the widely-used
package digest](https://github.com/eddelbuettel/digest/blob/master/.travis.yml) for an example of
running Linux and macOS at Travis.

Now, _the same script_ can be use _with the same steps_ at GitHub Actions. See [this script of the
newer package
tidyCpp](https://github.com/eddelbuettel/tidycpp/blob/master/.github/workflows/R-CMD-check.yaml)
also running Linux and macOS at GitHub Actions.

Similarly, _the same script_ has been used (just to prove the point) with Azure Pipelines.

And best of all you can also run it at home in Docker container to debug your setup.

### More

See the [public webpage for r-travis](http://eddelbuettel.github.io/r-travis/) for more.

### Author

Dirk Eddelbuettel (for this maintained fork)

Craig Citro, Kirill Mueller, Dirk Eddelbuettel, ... (for the original r-travis)
