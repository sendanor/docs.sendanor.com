# Pipeline model

Our *Pipeline models* are instructions for the [Pipeline Runner software](../runner/index.md) to 
execute operations on a system.

Usually it is the local system where the software is running. However, our runner has a pluggable 
architecture which could support running actions on another system in the future.

These models are JSON data structures encoded as UTF-8 character set.

## We have four types of pipeline models

* [*Pipeline*](pipeline.md) defines one or more [*stages*](./stage.md) to be executed in the same order as they are defined
* [*Stage*](stage.md) defines one or more [*jobs*](./job.md) to be executed in parallel at the same time
* [*Job*](job.md) defines one or more [*steps*](./step/index.md) to be executed in the same order as they are defined
* [*Step*](step/index.md) defines a work item to execute

All these models also support [parameters](./parameters.md) and [variables](./variables.md) on their top level.
