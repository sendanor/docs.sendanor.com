# The CSV Step model

*CSV-step* defines operation to parse or stringify CSV values.

## Stringify variable as CSV

=== "JSON"

    ```json
    {
      "name": "Stringify_csv",
      "csv": [
        ["foo1", "bar1"],
        ["foo2", "bar2"],
        ["foo,2", "bar,2"],
        ["\"foo\",2", "bar,2"]
      ],
      "action": "stringify",
      "output": "csvString"
    }
    ```

=== "Properties"

    | Property     | Type               | Summary                                              |
    | ------------ | ------------------ | ---------------------------------------------------- |
    | `name`       | `string`           | The name of the job                                  |
    | `csv`        | `JsonAny`          | The value to stringify                       |
    | `action`     | `JsonAny`          | Action to do                                         |
    | `output`     | `string`           | Optional variable name to save the result            |
    | `parameters` | `ParameterModel[]` | Optional [pipeline parameters](../parameters.md)     |
    | `variables`  | `JsonObject`       | Optional [pipeline variables](../variables.md)       |

## Parse CSV to variable

=== "JSON"

    ```json
    {
      "name": "Parse_csv",
      "csv": "${csvString}",
      "action": "parse",
      "output": "csvList"
    }
    ```

=== "Properties"

    | Property     | Type               | Summary                                              |
    | ------------ | ------------------ | ---------------------------------------------------- |
    | `name`       | `string`           | The name of the job                                  |
    | `csv`        | `JsonAny`          | The value to parse                       |
    | `action`     | `JsonAny`          | Action to do                                         |
    | `output`     | `string`           | Optional variable name to save the result            |
    | `parameters` | `ParameterModel[]` | Optional [pipeline parameters](../parameters.md)     |
    | `variables`  | `JsonObject`       | Optional [pipeline variables](../variables.md)       |

