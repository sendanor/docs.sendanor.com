# Pipeline parameters

Any pipeline model can define input parameters from the outside, eg. [forms](../../forms/configuring-pipeline.md).

=== "String"

    ```json
    {
        "parameters": [
            {
                "type": "string",
                "name": "format",
                "displayName": "Date Format",
                "default": "%s"
            }
        ],
        "name": "Print_date_with_params",
        "command": "date",
        "args": [
            "+${{format}}"
        ]
    }
    ```
    
    This pipeline defines one optional input parameter named `format` which must be a string.

=== "Number"

    ```json
    {
        "parameters": [
            {
                "type": "number",
                "name": "value",
                "displayName": "Input value",
                "default": 123.456
            }
        ],
        "name": "Print_value",
        "command": "echo",
        "args": [
            "${{value}}"
        ]
    }
    ```
    
    This pipeline defines one optional input parameter named `value` which must be a number.

=== "Integer"

    ```json
    {
        "parameters": [
            {
                "type": "integer",
                "name": "value",
                "displayName": "Input value",
                "default": 123
            }
        ],
        "name": "Print_value",
        "command": "echo",
        "args": [
            "${{value}}"
        ]
    }
    ```
    
    This pipeline defines one optional input parameter named `value` which must be a integer.

=== "Boolean"

    ```json
    {
        "parameters": [
            {
                "type": "boolean",
                "name": "value",
                "displayName": "Input value",
                "default": false
            }
        ],
        "name": "Print_value",
        "command": "echo",
        "args": [
            "${{value}}"
        ]
    }
    ```
    
    This pipeline defines one optional input parameter named `value` which must be a boolean.

=== "JSON"

    ```json
    {
        "parameters": [
            {
                "type": "json",
                "name": "items",
                "displayName": "Input value",
                "default": [
                  "foo", 
                  "bar"
                ]
            }
        ],
        "name": "Print_value",
        "command": "echo",
        "args": "${{items}}"
    }
    ```
    
    This pipeline defines one optional input parameter named `items` which must be valid JSON.

The parameter must be referenced as `${{NAME}}` because parameters are compiled 
before the pipeline is started, and so do not exist anymore while the pipeline is executing.
