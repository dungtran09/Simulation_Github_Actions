[![Hello_workflow](https://github.com/dungtran09/github-actions/actions/workflows/actions.yaml/badge.svg)](https://github.com/dungtran09/github-actions/actions/workflows/actions.yaml)

# simple-action

> A very simple GitHub action implementing the command design pattern

## Context post

This repository is an example action adopting the design pattern discussed in this blog post: [Adopting the command design pattern for GitHub Actions](https://blog.bassemdy.com/2021/04/05/github/actions/design-patterns/command/best-practices/adopt-command-pattern-for-actions.html)

## Usage

### Workflow setup

```yaml
name: Hello_workflow

on:
  push:
    branches:
      - main
    pull_request:
      branches:
        - main
    workflow_dispatch:
# Jobs simulation
jobs:
  hello:
    runs-on: ubuntu-latest
    # Because the action is hosted in this same repository and it has not
    # been published to the marketplace, we have to checkout the repo
    # so that we can call the local action in the next steps
    steps:
      - uses: actions/checkout@v2
      - name: Hello word
        # Print output from first step
        run: echo "Hello github"
        shell: bash

  goodbye:
    runs-on: ubuntu-latest
    steps:
        - name: Goodbye see you later
        # Print output from second steps
        run: echo "Goodbye github"
        shell: bash

```

## License

- [MIT License](./LICENSE)
