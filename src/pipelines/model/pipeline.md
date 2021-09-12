# The Pipeline model

*Pipeline* defines one or more [*stages*](./stage.md) to be executed in the same order as they are defined.

The next stage will be started once the previous has been finished successfully.

Otherwise, when a stage fails, it will not continue to the next one.

=== "JSON"

    ```json
    {
      "name": "My_pipeline",
      "stages": [
        {
          "name": "My_stage",
          "jobs": [
            {
              "name": "My_job",
              "steps": [
                {
                  "name": "Print_date",
                  "command": "date"
                }
              ]
            }
          ]
        }
      ]
    }
    ```

=== "Properties"

    | Property | Type      | Summary                          |
    | -------- | --------- | -------------------------------- |
    | `name`   | `string`  | The name of the pipeline         |
    | `stages` | `Stage[]` | One or more [stages](./stage.md) |
    | `parameters` | `ParameterModel[]` | Optional [pipeline parameters](./parameters.md) |
    | `variables`  | `JsonObject`       | Optional [pipeline variables](./variables.md)   |

=== "TypeScript interface"

    ```typescript
    interface Pipeline {
        readonly name        : string;
        readonly stages      : readonly Stage[];
        readonly parameters ?: ParameterModel[]   | undefined;
        readonly variables  ?: ReadonlyJsonObject | undefined;
    }
    ```

