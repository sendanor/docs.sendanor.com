# Pipeline variables

Any pipeline model can define runtime variables.

```json
{
    "variables": {
      "format": "+%s"
    },
    "name": "Print_date_with_params",
    "command": "date",
    "args": [
        "+${format}"
    ]
}
```

This pipeline defines one input variable named `format` which is a string `"+%s"`.
