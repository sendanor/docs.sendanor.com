# The Concat Step model

*Concat* defines an operation to join multiple values as one.

## Join arrays as one array

=== "JSON"

    ```json
    {
      "name": "Create_MyList",
      "concat": [
        "${otherList}",
        [
          {
            "name": "MyNewItem"
          }
        ]
      ],
      "output": "MyList"
    }
    ```

=== "Result"

    The result will be saved as `MyList` variable:

    ```json
    [
      {
        "name": "ItemFromOtherList"
      },
      {
        "name": "MyNewItem"
      }
    ]
    ```

=== "Properties"

    | Property     | Type               | Summary                                         |
    | ------------ | ------------------ | ----------------------------------------------- |
    | `name`       | `string`           | The name of the job                             |
    | `concat`     | `JsonAny`          | Any JSON value                                  |
    | `output`     | `string`           | The variable name to save the result            |
    | `parameters` | `ParameterModel[]` | Optional [pipeline parameters](../parameters.md)     |
    | `variables`  | `JsonObject`       | Optional [pipeline variables](../variables.md)       |


## Merge objects as one

=== "JSON"

    ```json
    {
      "name": "Create_MyObject",
      "concat": [
          {
            "name": "MyNewItem"
          },
          {
            "content": "MyContent"
          },
          "${myObject}"
        ]
      ],
      "output": "MyObject"
    }
    ```

=== "Result"

    The result will be saved as `MyObject` variable:

    ```json
    {
      "name": "MyNewItem"
      "content": "MyContent",
      "some": "propertyFromMyObject"
    }
    ```

=== "Properties"

    | Property     | Type               | Summary                                         |
    | ------------ | ------------------ | ----------------------------------------------- |
    | `name`       | `string`           | The name of the job                             |
    | `concat`     | `JsonAny`          | Any JSON value                                  |
    | `output`     | `string`           | The variable name to save the result            |
    | `parameters` | `ParameterModel[]` | Optional [pipeline parameters](../parameters.md)     |
    | `variables`  | `JsonObject`       | Optional [pipeline variables](../variables.md)       |


## Join array of strings as one

=== "JSON"

    ```json
    {
      "name": "Create_MyObject",
      "concat": [
          "MyNewItem ",
          "MyContent ",
          "${myString}"
        ]
      ],
      "output": "MyString"
    }
    ```

=== "Result"

    The result will be saved as `MyString` variable:

    ```json
    "MyNewItem MyContent SomethingFromMyString"
    ```

=== "Properties"

    | Property     | Type               | Summary                                         |
    | ------------ | ------------------ | ----------------------------------------------- |
    | `name`       | `string`           | The name of the job                             |
    | `concat`     | `JsonAny`          | Any JSON value                                  |
    | `output`     | `string`           | The variable name to save the result            |
    | `parameters` | `ParameterModel[]` | Optional [pipeline parameters](../parameters.md)     |
    | `variables`  | `JsonObject`       | Optional [pipeline variables](../variables.md)       |

