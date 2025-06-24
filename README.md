# git-fetch-unshallow-buildkite-plugin

A Buildkite plugin that performs a git fetch to make a shallow clone deeper.

## Usage

Add the following to your pipeline:

```yml
steps:
  - plugins:
      - github.com/brexhq/git-fetch-unshallow-buildkite-plugin#v0.0.5
```

## Configuration

### `GIT_FETCH_COMMIT_DEPTH` (optional, environment variable)

Set this environment variable to specify the maximum commit depth for git fetch:

```yml
steps:
  - plugins:
      - github.com/brexhq/git-fetch-unshallow-buildkite-plugin#v0.0.5:
          env:
            GIT_FETCH_COMMIT_DEPTH: 1000
```

If not specified, the plugin will perform a `git fetch --unshallow` operation to fetch all commits.
