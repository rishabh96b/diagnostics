# diagnostics


## Getting Started

Build the CLI using `go build -o diagnostics .` and put it in `$PATH`. This binary acts as a plugin for the [dkp-cli](https://github.com/mesosphere/dkp-cli). Hence, this binary can be run either as a plugin to dkp cli or as standalone.

>**Note**: The `troubleshoot` package uses `github.com/containers/storage` package which needs `btrfs` headers to be present in the system. Devs using Ubuntu most likely will encounter errors while building the cli. In that case, run the below command.

```bash
sudo apt-get install libbtrfs-dev libdevmapper-dev
```

### Usage
```bash
./diagnostics /path/to/support-bundle-manifest.yaml
```
The above command will generate the support bundle named similar to `support-bundle-2021-09-16T04_58_32.tar.gz`.

### Cli Usage
```bash
A support bundle is an archive of files, output, metrics and state
from a server that can be used to assist when troubleshooting a Kubernetes cluster.

Usage:
  diagnostics [url] [flags]

Flags:
      --as string                      Username to impersonate for the operation
      --as-group stringArray           Group to impersonate for the operation, this flag can be repeated to specify multiple groups.
      --cache-dir string               Default cache directory (default "/home/rishabh/.kube/cache")
      --certificate-authority string   Path to a cert file for the certificate authority
      --client-certificate string      Path to a client certificate file for TLS
      --client-key string              Path to a client key file for TLS
      --cluster string                 The name of the kubeconfig cluster to use
      --collect-without-permissions    always generate a support bundle, even if it some require additional permissions (default true)
      --context string                 The name of the kubeconfig context to use
  -h, --help                           help for diagnostics
      --insecure-skip-tls-verify       If true, the server's certificate will not be checked for validity. This will make your HTTPS connections insecure
      --kubeconfig string              Path to the kubeconfig file to use for CLI requests.
  -n, --namespace string               If present, the namespace scope for this CLI request
      --redact                         enable/disable default redactions (default true)
      --redactors strings              names of the additional redactors to use
      --request-timeout string         The length of time to wait before giving up on a single server request. Non-zero values should contain a corresponding time unit (e.g. 1s, 2m, 3h). A value of zero means don't timeout requests. (default "0")
  -s, --server string                  The address and port of the Kubernetes API server
      --since string                   force pod logs collectors to return logs newer than a relative duration like 5s, 2m, or 3h.
      --since-time string              force pod logs collectors to return logs after a specific date (RFC3339)
      --tls-server-name string         Server name to use for server certificate validation. If it is not provided, the hostname used to contact the server is used
      --token string                   Bearer token for authentication to the API server
      --user string                    The name of the kubeconfig user to use
```