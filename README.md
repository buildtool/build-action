<p align="center">
  <h3 align="center">Buildtool Build Action</h3>
  <p align="center"><a href="https://github.com/features/actions">GitHub Action</a> for <a href="https://buildtools.io/commands/#build">Buildtool Build</a></p>
  <p align="center">
    <a href="https://github.com/buildtool/build-action/releases/latest"><img alt="GitHub release" src="https://img.shields.io/github/release/buildtool/build-action.svg?logo=github"></a>
  </p>
</p>

---

> **:warning: Note:** To use this action, you must have access to the [GitHub Actions](https://github.com/features/actions) feature. GitHub Actions are currently only available in public beta. You can [apply for the GitHub Actions beta here](https://github.com/features/actions/signup/).

## Usage

Below is a simple snippet to use this action.

```yaml
name: buildtool

on:
  pull_request:
  push:

jobs:
  goreleaser:
    runs-on: ubuntu-latest
    steps:
      -
        name: Checkout
        uses: actions/checkout@master
      -
        name: Set up Go
        uses: actions/setup-go@master
      -
        name: Run build-tools build command
        uses: buildtools/build-action@v1
```

## Customizing

### Inputs

Following inputs can be used as `step.with` keys

| Name                      | Type    | Default   | Description                              |
|---------------------------|---------|-----------|------------------------------------------|
| ` additional-docker-args` | String  |           | Extra arguments to `docker build`, supports  `-f <Dockerfile>` and multiple `--build-arg <KEY>=<VALUE>` params  |

## License

MIT. See `LICENSE` for more details.