# The Variable Step model

*Variable* defines an operation to set a named variable.

## Set a variable

The value `gitDir` will be set as `TEMP_DIR/git`:

=== "JSON"

    ```json
    {
      "name": "Set_variable",
      "variable": "gitDir",
      "set": "${tempDir}/git"
    }
    ```

=== "Properties"

    | Property     | Type               | Summary                                              |
    | ------------ | ------------------ | ---------------------------------------------------- |
    | `name`       | `string`           | The name of the job                                  |
    | `variable`   | `string`           | The name of the variable to set                      |
    | `set`        | `JsonAny`          | The new value to the variable                        |
    | `parameters` | `ParameterModel[]` | Optional [pipeline parameters](../parameters.md)     |
    | `variables`  | `JsonObject`       | Optional [pipeline variables](../variables.md)       |

