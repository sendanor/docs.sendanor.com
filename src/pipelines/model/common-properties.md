# Common model properties

Every model can define following top level properties:

=== "Properties"

    | Property       | Type               | Summary                                                     |
    | -------------- | ------------------ | ----------------------------------------------------------- |
    | `name`         | `string`           | The name of the job. See [Naming rules](./naming-rules.md). |
    | `displayName`  | `string`           | Optional. Display name of the job(*). Defaults to `name`. See [Naming rules](./naming-rules.md).  |
    | `parameters`   | `ParameterModel[]` | Optional. [Parameters](./parameters.md)                     |
    | `variables`    | `JsonObject`       | Optional. [Variables](./variables.md)                       |

    *) The `displayName` is not yet implemented -- but is planned.

=== "JSON"

    ```json
    {
      "parameters": [
        {
          "type": "string",
          "name": "foo",
          "displayName": "Foo value",
          "default": ""
        }
      ],
      "name": "My_job",
      "displayName": "My Job",
      "variables": {
        "bar": "Hello world"
      },
      "steps": [
        {
          "name": "Print",
          "command": "echo",
          "args": [
            "${{foo}}",
            "${bar}"
          ]
        }
      ]
    }
    ```

=== "TypeScript interface"

    ```typescript
    interface PipelineModel {
        readonly name         : string;
        readonly displayName ?: string;
        readonly parameters  ?: ParameterModel[]   | undefined;
        readonly variables   ?: ReadonlyJsonObject | undefined;
    }
    ```
