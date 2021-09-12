# The Git Step model

*Git* defines operations on the git repository.

*Note!* The `git` command is required on the system.

## Clone a repository

This step clones a repository by running a command `git clone URL [TARGET]`.

=== "Example"

    ```json
    {
      "name": "Prepare_git",
      "git": "clone",
      "url": "git@github.com:sendanor/ts.git",
      "target": "${gitDir}"
    }
    ```

=== "Properties"

    | Property     | Type               | Summary                                              |
    | ------------ | ------------------ | ---------------------------------------------------- |
    | `name`       | `string`           | The name of the step                                 |
    | `git`        | `string`           | The action to execute                                |
    | `url`        | `string`           | The git repository to clone (may be a file, too)     |
    | `target`     | `string`           | Optional target location to clone into. Defaults to the repository name. |

## Add a file in repository

This step runs `git add TARGET`, optionally changing the working directory to `cwd`.

=== "Example"

    ```json
    {
      "name": "Add_to_git",
      "git": "add",
      "target": "${commentFile}",
      "cwd": "${gitDir}"
    }
    ```

=== "Properties"

    | Property     | Type               | Summary                                              |
    | ------------ | ------------------ | ---------------------------------------------------- |
    | `name`       | `string`           | The name of the step                                 |
    | `git`        | `string`           | The action to execute                                |
    | `target`     | `string`           | The git file or directory to add to be commited. Defaults to `.`, eg. current directory. |
    | `cwd`        | `string`           | Optional directory to change the working directory   |

## Pull changes from remote repository

This step runs `git pull [TARGET]`, optionally changing the working directory to `cwd`.

=== "Example"

    ```json
    {
      "name": "Pull_changes",
      "git": "pull",
      "cwd": "${gitDir}"
    }
    ```

=== "Properties"

    | Property     | Type               | Summary                                              |
    | ------------ | ------------------ | ---------------------------------------------------- |
    | `name`       | `string`           | The name of the step                                 |
    | `git`        | `string`           | The action to execute                                |
    | `target`     | `string`           | Optional git url or directory where to push new commits. Defaults to origin. |
    | `cwd`        | `string`           | Optional directory to change the working directory. Defaults to the current directory.                           |

## Push changes to remote repository

This step runs `git push [TARGET]`, optionally changing the working directory to `cwd`.

=== "Example"

    ```json
    {
      "name": "Push_to_git",
      "git": "push",
      "cwd": "${gitDir}"
    }
    ```

=== "Properties"

    | Property     | Type               | Summary                                              |
    | ------------ | ------------------ | ---------------------------------------------------- |
    | `name`       | `string`           | The name of the step                                 |
    | `git`        | `string`           | The action to execute                                |
    | `target`     | `string`           | Optional git url or directory where to push new commits. Defaults to origin. |
    | `cwd`        | `string`           | Optional directory to change the working directory. Defaults to the current directory.                           |

## Set repository configurations

This step runs `git config [SET [VALUE]]`, optionally changing the working directory to `cwd`.

=== "Example"

    ```json
    {
      "name": "Set_git_email",
      "git": "config",
      "set": "user.email",
      "value": "agent@exmaple.com",
      "cwd": "${gitDir}"
    }
    ```

=== "Properties"

    | Property     | Type               | Summary                                              |
    | ------------ | ------------------ | ---------------------------------------------------- |
    | `name`       | `string`           | The name of the step                                 |
    | `git`        | `string`           | The action to execute                                |
    | `set`        | `string`           | The property name to set                             |
    | `value`      | `string`           | The property value to set                            |
    | `cwd`        | `string`           | Optional directory to change the working directory. Defaults to the current directory.                           |

## Commit changes

This step runs `git commit [-m MESSAGE]`, optionally changing the working directory to `cwd`.

=== "Example"

    ```json
    {
      "name": "Commit_git",
      "git": "commit",
      "message": "Pipeline changed files",
      "cwd": "${gitDir}"
    }
    ```

=== "Properties"

    | Property     | Type               | Summary                                              |
    | ------------ | ------------------ | ---------------------------------------------------- |
    | `name`       | `string`           | The name of the step                                 |
    | `git`        | `string`           | The action to execute                                |
    | `message`    | `string`           | The optional commit message. Defaults to `Pipeline commit`. |
    | `cwd`        | `string`           | Optional directory to change the working directory. Defaults to the current directory.                           |

