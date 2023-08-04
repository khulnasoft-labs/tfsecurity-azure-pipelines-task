## Installation

1. Install the tfsecurity task in your Azure DevOps organization (hit the `Get it free` button above).

2. Add the task to your `azure-pipelines.yml` in a project where you'd like to run tfsecurity:

```yaml
- task: tfsecurity@1
```

## Configuration

You can supply several inputs to customise the task.

### Enable debug mode

Add debug logs to the task output.

```yaml
- task: tfsecurity@1
  inputs:
    debug: true
```

### Specify tfsecurity version

Run a specific version of tfsecurity.

```yaml
- task: tfsecurity@1
  inputs:
    version: v1.26.0
```

### Specify custom command line options

```yaml
- task: tfsecurity@1
  inputs:
    args: --workspace my-workspace --config-file ./tfsecurity.yml
```

### Specify the directory to scan

```yaml
- task: tfsecurity@1
  inputs:
    dir: ./terraform
```

### Skip publishing test results

Avoid results showing the in 'Tests' tab of the Pipelines UI.

```yaml
- task: tfsecurity@1
  inputs:
    publishTestResults: false
```

### Informational only

If you'd like to see the tfsecurity results in your build, but avoid causing it to fail when issues are discovered, you can add the `--soft-fail` flag to your command line arguments using:

```yaml
- task: tfsecurity@1
  inputs:
    args: --soft-fail
```
