# helm-examples
helm template examples.

### Numeric loop

Create a numeric looping from 0 to n by set a integer value in `values.yaml`

```
$ cat values.yaml
count: 3

$ cat templates/loop.yaml
{{ $count := .Values.count | int  }}
{{- range until $count }}
count to {{.}}
{{- end }}
```

It will produce

```
count to 0
count to 1
count to 2
```

further more, you can change the pipeline function from `until` to `untilStep` to custom the range and step of loop variable.

```yaml
{{- range until 0 10 2 }}
count to {{.}}
{{- end }}
```

It will produce

```
count to 0
count to 2
count to 4
count to 6
count to 8
```
