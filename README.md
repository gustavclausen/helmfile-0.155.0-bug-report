# helmfile-0.155.0-bug-report

## Steps To Reproduce

1. Execute any command targeting either `stage` or `prod` that only includes a
   subset of all releases in the project. Example:
   `helmfile list --environment stage`.
2. Observe error message for the `telepresence` helmfile that is not targeting
   the `stage` nor `prod` environment:
   ```
   in ./helmfile.yaml: in .helmfiles[1]: in releases/telepresence/helmfile.yaml: error during helmfile.yaml.part.1 parsing: template: stringTemplate:16:40: executing "stringTemplate" at <.Values.groups>: map has no entry for key "groups"
   ```
