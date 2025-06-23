# git-fetch-unshallow-buildkite-plugin

A Buildkite plugin that performs a git fetch to make a shallow clone deeper.

## Usage

Add the following to your `pipeline.yml`:

```yml
steps:
  - plugins:
      - brexhq/git-fetch-unshallow#v1.0.0: {}
```

## Configuration

### `GIT_FETCH_COMMIT_DEPTH` (optional, environment variable)

Set this environment variable to specify the maximum commit depth for git fetch:

```yml
steps:
  - env:
      GIT_FETCH_COMMIT_DEPTH: "100"
    plugins:
      - brexhq/git-fetch-unshallow#v1.0.0: {}
```

If not specified, the plugin will perform a `git fetch --unshallow` operation to fetch all commits.
