# git Cheatsheet


## Remotes
| Task                            | Command |
|---------------------------------|---------|
| Set default upstream branch[^1] | `git config push.default {remote-name}` |

## Local Filesystem 
| Task                            | Command |
|---------------------------------|---------|
| Delete a **file** from repo without deleting local file | `git rm --cached {file-name}` |
| Delete a **directory** from repo without deleting local directory | `git rm --cached -r {directory-name}` |


<style>
    table code {
        white-space:nowrap;
        -moz-user-select: all;
        -webkit-user-select: all;
        -ms-user-select: all;
    }
</style>


[^1]: [:fontawesome-brands-stack-overflow: Git push: set target for branch][1]

[1]: https://stackoverflow.com/a/8172215/1356593