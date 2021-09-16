# diagnostics

## Getting Started

Build the CLI using `go build -o dkp-diagnostics .` and put it in `$PATH`. This binary acts as a plugin for the [dkp-cli](https://github.com/mesosphere/dkp-cli). Hence, this binary can be run either as a plugin to dkp cli or as standalone.


### Usage
```bash
dkp diagnostics /path/to/support-bundle-manifest.yaml
```
The above command will generate the support bundle named similar to `support-bundle-2021-09-16T04_58_32.tar.gz`.
