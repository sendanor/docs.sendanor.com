# The JSON Step model

*JSON* defines operation to parse or stringify values as JSON.

=== "Stringify as JSON"

    ```json
    {
      "name": "Stringify_json",
      "json": {"foo":"bar"},
      "action": "stringify",
      "output": "jsonString"
    }
    ```

    The value will be stringified as `"{\"foo\":\"bar\"}"` and saved to variable `jsonString`.

=== "Parse JSON"

    ```json
    {
      "name": "Parse_json",
      "json": "{\"foo\":\"bar\"}",
      "action": "parse",
      "output": "jsonObject"
    }
    ```

    The value will be parsed as `{"foo":"bar"}` and saved to variable `jsonObject`.

=== "Properties"

    | Property     | Type               | Summary                                              |
    | ------------ | ------------------ | ---------------------------------------------------- |
    | `name`       | `string`           | The name of the job                                  |
    | `json`       | `JsonAny`          | The value to perform an action                       |
    | `action`     | `JsonAny`          | Action to do                                         |
    | `output`     | `string`           | Optional variable name to save the result            |
    | `parameters` | `ParameterModel[]` | Optional [pipeline parameters](../parameters.md)     |
    | `variables`  | `JsonObject`       | Optional [pipeline variables](../variables.md)       |

