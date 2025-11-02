# Setup Flowcraft GitHub Action

This action downloads a specific version of the [Flowcraft CLI](https://github.com/Purpose-Dev/flowcraft) from its
GitHub Releases page, extracts it, and adds the binary to the `PATH` for use in subsequent workflow steps.

## Usage

Add the following step to your workflow file. This will install the `flowcraft` binary, making it available for commands
like `flowcraft run` or `flowcraft validate`.

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Check out code
        uses: actions/checkout@v4

      - name: Setup Flowcraft
        uses: Purpose-Dev/setup-flowcraft-action@v1
        with:
          version: 'v0.1.1' # Specify the version of flowcraft you want to use

      - name: Validate pipeline
        run: flowcraft validate

      - name: Run pipeline
        run: flowcraft run
```

## Inputs

### `version`

**Required.** The version of Flowcraft to install (e.g., `v0.1.1`). This must be a valid tag from
the [Flowcraft releases page](https://github.com/Purpose-Dev/flowcraft/releases).

---

## License

Flowcraft is released under the **Apache 2.0 License**. You can find the full license text in the [`LICENSE`](LICENSE)
file included in this repository.

Copyright 2025 Riyane El Qoqui.
