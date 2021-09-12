# The step model

*Steps* are directions for the agent to do a specific action.

=== "Example"

    ```json
    {
      "name": "Print_date",
      "command": "date"
    }
    ```

=== "Properties"

    | Property     | Type               | Summary                                      |
    | ------------ | ------------------ | -------------------------------------------- |
    | `name`       | `string`           | The name of the step                         |
    | `parameters` | `ParameterModel[]` | Optional [pipeline parameters](../parameters.md)     |
    | `variables`  | `JsonObject`       | Optional [pipeline variables](../variables.md)       |
    | *            | *                  | Other properties specific to the step's type |

=== "TypeScript interface"

    ```typescript
    interface Job {
        readonly name        : string;
        readonly steps       : readonly Step[];
        readonly parameters ?: ParameterModel[]   | undefined;
        readonly variables  ?: ReadonlyJsonObject | undefined;
    }
    ```

We have the following step types:

 * [Command](./command.md) defines a command to execute
 * [Git](./git.md) defines a git operation
 * [File](./file.md) defines a file operation
 * [JSON](./json.md) defines an operation with JSON format
 * [CSV](./csv.md) defines an operation with CSV format
 * [Assert](./assert.md) defines an assertion
 * [Concat](./concat.md) defines a concat operation
 * [Variable](./variable.md) defines an variable assign operation
