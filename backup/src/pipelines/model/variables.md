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

The variables can be referenced as `${NAME}` and value can be changed on runtime through other steps.

It's possible to reference a value inside an object by `${OBJ_NAME.NAME}`.
