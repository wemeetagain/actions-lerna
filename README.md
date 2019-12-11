# GitHub Actions for Lerna

This Action for [lerna](https://lerna.js.org) enables arbitrary actions with the `lerna` command-line client.

## Usage

An example workflow how to install packages and test via lerna:

```yml
name: CI
on: [push]
jobs:
  build:
    name: Test
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v1
      - uses: wemeetagain/actions-lerna@v0.1.0
        with:
          cmd: bootstrap # will run `lerna bootstrap` command
      - uses: wemeetagain/actions-lerna@v0.1.0
        with:
          cmd: run build # will run `lerna run build` command
      - uses: wemeetagain/actions-lerna@v0.1.0
        with:
          cmd: run test # will run `lerna run test` command
```

> `cmd` value will be used as a command for Lerna

## License

MIT
