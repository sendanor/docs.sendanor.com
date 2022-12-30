# The File Step model

*File* defines operations on the File system.

## Create a temporary directory

This step creates a temporary directory. 

It will be removed after the pipeline has stopped running.

=== "JSON"

    ```json
    {
      "name": "Prepare_temp_dir",
      "file": "mkdir",
      "output": "tempDir"
    }
    ```

=== "Properties"

    | Property     | Type               | Summary                                              |
    | ------------ | ------------------ | ---------------------------------------------------- |
    | `name`       | `string`           | The name of the step                                 |
    | `file`       | `JsonAny`          | The action to execute                                |
    | `output`     | `string`           | Variable name to save the file name                  |

## Create a specific directory

This step creates a directory to the target location.

=== "JSON"

    ```json
    {
      "name": "Prepare_dir",
      "file": "mkdir",
      "target": "${tempDir}/myPath"
    }
    ```

=== "Properties"

    | Property     | Type               | Summary                                              |
    | ------------ | ------------------ | ---------------------------------------------------- |
    | `name`       | `string`           | The name of the step                                 |
    | `file`       | `JsonAny`          | The action to execute                                |
    | `target`     | `string`           | The target directory to create                       |
    | `output`     | `string`           | Optional variable name to save the directory name    |

## Read file to string

This step will read file from the target location to a variable as string (using UTF-8 encoding).

=== "JSON"

    ```json
    {
      "name": "Read_file",
      "file": "read",
      "target": "${tempDir}/myPath.txt",
      "output": "fileContents"
    }
    ```

=== "Properties"

    | Property     | Type               | Summary                                              |
    | ------------ | ------------------ | ---------------------------------------------------- |
    | `name`       | `string`           | The name of the step                                 |
    | `file`       | `JsonAny`          | The action to execute                                |
    | `target`     | `string`           | The target file to read                              |
    | `output`     | `string`           | Variable name to save the file contents              |

## Read or create a file on the File system

This step will read a file from the target location to a variable as string (using UTF-8 encoding) if it exists.

Otherwise, it will create it.

=== "JSON"

    ```json
    {
      "name": "Read_or_create_file",
      "file": "read/create",
      "target": "${tempDir}/myPath.txt",
      "default": "[]",
      "output": "itemsJsonString"
    }
    ```

=== "Properties"

    | Property     | Type               | Summary                                              |
    | ------------ | ------------------ | ---------------------------------------------------- |
    | `name`       | `string`           | The name of the step                                 |
    | `file`       | `JsonAny`          | The action to execute                                |
    | `target`     | `string`           | The target file to read                              |
    | `default`    | `string`           | The content of the file if it does not exist         |
    | `output`     | `string`           | Variable name to save the file contents              |

## Write file as string

This step will write the `content` property as a string to a file on the target location (using UTF-8 encoding).

=== "JSON"

    ```json
    {
      "name": "Write_file",
      "file": "write",
      "target": "${tempDir}/myPath.txt",
      "content": "Hello world\n",
      "output": "myFileName"
    }
    ```

=== "Properties"

    | Property     | Type               | Summary                                              |
    | ------------ | ------------------ | ---------------------------------------------------- |
    | `name`       | `string`           | The name of the step                                 |
    | `file`       | `JsonAny`          | The action to execute                                |
    | `target`     | `string`           | The target file to write to                          |
    | `content`    | `string`           | The file contents as a string                        |
    | `output`     | `string`           | Variable name to save the file target name           |

## Write file as JSON

This step will write the `content` property to a file on the target location (using JSON and UTF-8 encoding).

=== "JSON"

    ```json
    {
      "name": "Write_file",
      "file": "write",
      "target": "${tempDir}/myPath.txt",
      "content": {
        "hello": "world"
      },
      "output": "myFileName"
    }
    ```

=== "Properties"

    | Property     | Type               | Summary                                                          |
    | ------------ | ------------------ | ---------------------------------------------------------------- |
    | `name`       | `string`           | The name of the step                                             |
    | `file`       | `JsonAny`          | The action to execute                                            |
    | `target`     | `string`           | The target file to write to                                      |
    | `content`    | `JsonAny`          | The file contents as a any JSON compatible value (except string) |
    | `output`     | `string`           | Variable name to save the file target name                       |
