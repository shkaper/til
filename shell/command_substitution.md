Q: Assuming `files.txt` has a list of file names, what's the easy way to `rm` the files?

A: Using the command substitution via `$(...)`
```shell
rm $(cat files.txt)
```
or via the backticks:
```shell
rm `cat files.txt`
```
The latter is not recommended though, as the `$(...)` is easier to nest.
