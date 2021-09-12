# The Job model

*Job* defines one or more [*steps*](./step/index.md) to be executed in the same order as they are defined.

The next step will be started once the previous has been finished successfully.

Otherwise, if step fails, it will not continue and the job is marked as failed.

=== "JSON"

    ```json
    {
      "name": "My_job",
      "steps": [
        {
          "name": "Print_date",
          "command": "date"
        }
      ]
    }
    ```

=== "Properties"

    | Property | Type      | Summary                              |
    | -------- | --------- | ------------------------------------ |
    | `name`   | `string`  | The name of the job                  |
    | `steps`  | `Step[]`  | One or more [steps](./step/index.md) |
    | `parameters` | `ParameterModel[]` | Optional [pipeline parameters](./parameters.md) |
    | `variables`  | `JsonObject`       | Optional [pipeline variables](./variables.md)   |

=== "TypeScript interface"

    ```typescript
    interface Job {
        readonly name        : string;
        readonly steps       : readonly Step[];
        readonly parameters ?: ParameterModel[]   | undefined;
        readonly variables  ?: ReadonlyJsonObject | undefined;
    }
    ```

