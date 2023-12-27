# Setup `gsoc2-terraform-provider`

This action configures the use of the Gsoc2 terraform provider for a
particular Gsoc2 environment.  There are two main things this does:
1. Installs/Authenticates `chainctl` for the particular environment,
2. Configure a `~/.terraformrc` that pulls the Gsoc2 provider from our GCS
  bucket for this environment.

## Usage

```yaml
- uses: gsoc2/actions/setup-gsoc2-terraform@main
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
- uses: gsoc2/actions/setup-gsoc2-terraform@main
  with:
    identity: "deadbeef/badf00d"
```
