# The Assert Step model

*Assert* defines operation to check if two values are equal.

The step will fail if these values do not match.

=== "Example"

    ```json
    {
      "name": "Check_value",
      "assert": "${something}"
      "equals": "FooBar"
    }
    ```

=== "Properties"

    | Property     | Type               | Summary                                              |
    | ------------ | ------------------ | ---------------------------------------------------- |
    | `name`       | `string`           | The name of the job                                  |
    | `assert`     | `JsonAny`          | The value to check against                           |
    | `equals`     | `JsonAny`          | The value to check for                               |
    | `output`     | `string`           | Optional variable name to save the result as boolean. This will always be true or not defined. |
    | `parameters` | `ParameterModel[]` | Optional [pipeline parameters](../parameters.md)     |
    | `variables`  | `JsonObject`       | Optional [pipeline variables](../variables.md)       |

