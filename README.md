# prek GitHub Action

This GitHub Action runs [prek](https://github.com/j178/prek) for automated code checks in your repository.

As it stands this is a drop-in replacement for <https://github.com/pre-commit/action>: migration should be as simple as updating the action used.

> [!WARNING]
> This action is still in preview and like prek, is not recommended for production use.

## Features
- Installs `prek` and its hooks
- Caches prek hooks for faster runs
- Runs `prek` with customizable arguments

## Inputs
| Name       | Description                  | Required | Default     |
| ---------- | ---------------------------- | -------- | ----------- |
| extra_args | Additional arguments to prek | false    | --all-files |

## Usage
Add the following to your workflow YAML:

```yaml
jobs:
  prek:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: onerandomusername/prek-action@main
        with:
          extra_args: '--all-files' # optional
```

## Example
To run prek with default arguments:
```yaml
- uses: onerandomusername/prek-action@main
```

To pass custom arguments (eg to run flake8 separately):
```yaml
- uses: onerandomusername/prek-action@main
  with:
    extra_args: '--skip flake8'
```

## License
See [LICENSE](./LICENSE) for details.
