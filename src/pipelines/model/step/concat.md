# The Concat Step model

*Concat* defines an operation to join multiple values as one.

=== "Join arrays"

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

=== "Merge objects"

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

    The result will be saved as `MyObject` variable:

    ```json
    {
      "name": "MyNewItem"
      "content": "MyContent",
      "some": "propertyFromMyObject"
    }
    ```

=== "Join strings"

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

