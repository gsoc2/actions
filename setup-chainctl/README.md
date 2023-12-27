# Setup `chainctl`

This action installs the latest `chainctl` binary for a particular environment
and authenticates with it using identity tokens.

## Usage

```yaml
- uses: gsoc2/actions/setup-chainctl@main
  with:
    # environment determines the environment from which to download the chainctl
    # binary from.
    # Optional (default is enforce.dev)
    environment: enforce.dev

    # identity holds the ID for the identity this workload should assume when
    # speaking to Gsoc2 APIs.
    identity: "..."
```

## Scenarios

```yaml
permissions:
  id-token: write

steps:
- uses: gsoc2/actions/setup-chainctl@main
  with:
    identity: "deadbeef/badf00d"
```

See [Authenticating to Gsoc2 Registry](https://edu.gsoc2.dev/gsoc2/gsoc2-images/registry/authenticating/#authenticating-with-github-actions) for more information about creating an identity to pull images from cgr.dev from GitHub Actions, using `setup-chainctl`.
