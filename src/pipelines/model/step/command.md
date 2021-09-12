# The Command Step model

*Command* defines a command to be executed on the system where the agent runs.

## Execute a command

This step executes a command `date` on the system.

=== "Example"

    ```json
    {
      "name": "Print_date",
      "command": "date"
    }
    ```

=== "Properties"

    | Property     | Type               | Summary                                              |
    | ------------ | ------------------ | ---------------------------------------------------- |
    | `name`       | `string`           | The name of the step                                 |
    | `command`    | `string`           | The command's name to execute                        |

## Execute a command and save results

This step executes a command `date` on the system and saves results as `dateString` variable.

=== "Example"

    ```json
    {
      "name": "Get_date",
      "command": "date",
      "output": "dateString"
    }
    ```

=== "Properties"

    | Property     | Type               | Summary                                              |
    | ------------ | ------------------ | ---------------------------------------------------- |
    | `name`       | `string`           | The name of the step                                 |
    | `command`    | `string`           | The command's name to execute                        |
    | `output`     | `string`           | Optional output variable name                        |

## Execute a command with argument and save results

This step executes a command `date +%s` on the system and saves results as `timestampString` variable.

=== "Example"

    ```json
    {
      "name": "Get_timestamp",
      "command": "date",
      "args": [
        "+%s"
      ]
      "output": "timestampString"
    }
    ```

=== "Properties"

    | Property     | Type               | Summary                                              |
    | ------------ | ------------------ | ---------------------------------------------------- |
    | `name`       | `string`           | The name of the step                                 |
    | `command`    | `string`           | The command's name to execute                        |
    | `args`       | `string[]`         | Optional list of command's arguments                 |
    | `output`     | `string`           | Optional output variable name                        |

