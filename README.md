# Elixir Pre-commit Hooks

## Usage

Requires [pre-commit](https://pypi.org/project/pre-commit/).

Add the following to your pre-commit.config.yaml file:

```yaml
repos:
- repo: https://github.com/Appropriate-Solutions-Inc/elixir-pre-commit-hooks
  rev: v1.0.0  # replace with the version you want to use
  hooks:  # specify which hooks you want to use
    - id: mix-format
    - id: mix-test
    - id: mix-credo
```

Install the hooks:

```bash
$ pre-commit install
```

## Available Hooks

### `mix-format`

Runs `mix format` when an `.ex` or `.exs` file is included in the commit.

### `mix-test`

Runs `mix test` when an `.ex` file is included in the commit.

### `mix-credo`

Runs `mix credo` when an `.ex` file is included in the commit.

### `mix-dialyxir`

Runs `mix dialyxir` when an `.ex` file is included in the commit.
Use with caution as the analysis can be slow.

## `mix-escript-build`

Runs `mix escript.build` when an `.ex` or `exs` file is include in the commit.
Only useful when a project contains command line scripts.

## Passing Options to Hooks

If you want to pass additional options to the hook, you can include an `args` key in the hook's configuration in .pre-commit-config.yaml. The value of the key should be a list of the arguments you want to pass.

```yaml
hooks:
  - id: mix-test
    args: [--trace, --exclude, my-exclude-filter]
```

## Other Projects

- [elixir-pre-commit-hooks](https://gitlab.com/jvenom/elixir-pre-commit-hooks)
by Joshua David Vernon. This version is based on Joshua's and continues his MIT license.

- [elixir-pre-commit](https://github.com/dwyl/elixir-pre-commit) is an Elixir module that provides a pure-Elixir implementation of pre-commit Git hooks. You might want to use that if you only want mix tasks as your pre-commit hooks. If you want to use other, non-mix pre-commit hooks (like [these](https://github.com/pre-commit/pre-commit-hooks)) _and_ mix tasks, you should use this repo.
