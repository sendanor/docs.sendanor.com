# The Stage model

*Stage* defines one or more [*jobs*](./job.md) to be executed in parallel at the same time.

The stage is marked as finished once every job is done successfully.

Otherwise, if any job fails, the stage will be marked as failed.

=== "Example"

    ```json
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
    ```

=== "Properties"

    | Property | Type      | Summary                              |
    | -------- | --------- | ------------------------------------ |
    | `name`   | `string`  | The name of the stage                |
    | `jobs`   | `Job[]`   | One or more [jobs](./job.md)         |
    | `parameters` | `ParameterModel[]` | Optional [pipeline parameters](./parameters.md) |
    | `variables`  | `JsonObject`       | Optional [pipeline variables](./variables.md)   |

=== "TypeScript interface"

    ```typescript
    interface Stage {
        readonly name        : string;
        readonly jobs        : readonly Job[];
        readonly parameters ?: ParameterModel[]   | undefined;
        readonly variables  ?: ReadonlyJsonObject | undefined;
    }
    ```

