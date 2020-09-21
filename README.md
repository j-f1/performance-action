# performance-action

*A fork of Preact’s [compressed size action](https://github.com/preactjs/compressed-size-action).*

A GitHub action that reports changes in performance test results for JavaScriptKit.

### Usage:

Add a workflow (`.github/workflows/main.yml`):

```yaml
name: Performance

on: [pull_request]

jobs:
  build:

    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v2
    - uses: j-f1/performance-action@master
      with:
        repo-token: "${{ secrets.GITHUB_TOKEN }}"
        build-script: "make bootstrap build; cd IntegrationTests; make benchmark_setup"
        benchmark: "cd IntegrationTests; make -s run_benchmark"
```
