<p align="center">
  <h3 align="center">Buildtool Build Action</h3>
  <p align="center"><a href="https://github.com/features/actions">GitHub Action</a> for <a href="https://buildtools.io/commands/#build">Buildtool Build</a></p>
  <p align="center">
    <a href="https://github.com/buildtool/build-action/releases/latest"><img alt="GitHub release" src="https://img.shields.io/github/release/buildtool/build-action.svg?logo=github"></a>
    <a href="https://github.com/marketplace/actions/github-action-for-build"><img alt="GitHub marketplace" src="https://img.shields.io/badge/marketplace-build--action-blue?logo=github"></a>
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
        uses: actions/checkout@v1
      -
        name: Run build-tools build command
        uses: buildtool/build-action@v1
        with:
          dockerfile: dockerfiles/Dockerfile.build
          docker-build-args: '--build-arg abc=123'
```

## Customizing

### Inputs

Following inputs can be used as `step.with` keys

| Name                      | Type    | Default         | Description                                   |
|---------------------------|---------|-----------------|-----------------------------------------------|
| ` dockerfile`             | String  | `Dockerfile`    | To use a specific Dockerfile in your project  |
| ` docker-build-args`      | String  |                 | Docker [build-arg]                            |


## License

MIT. See `LICENSE` for more details.

[build-arg]: https://docs.docker.com/engine/reference/commandline/#set-build-time-variables---build-arg