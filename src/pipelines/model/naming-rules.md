# Model naming rules

The `name` property must:

 * ...be of type `string`
 * ...be at least one character long
 * ...be unique within the pipeline (*)
 * ...contain only characters `a-zA-Z0-9_-` (*)
 * ...**not** start with a number, e.g., `0-9` (*)
 * ...**not** contain secret information (**)

The `displayName` property -- if provided -- must:

 * ...be of type `string`
 * ...be at least one character long
 * ...**not** contain secret information (**)

*) Current implementation may not validate this yet

**) These values may be provided to a preview and visible to the end-user who started the pipeline
