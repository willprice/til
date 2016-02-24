# Packer
## Templating
(2016/02/24)

- `{{ .Var }}` to substitute a packer-defined variable.
- ``{{ user `varname` }}`` to substitute a user-defined variable.
- `{{ fn_name }}` to invoke a function called `fn_name`

### User variable definition
Variables can be defined in a json file and passed to packer with `-var-file`,
or specified on the cli using `-var 'key=val'`, or specified inside the
template itself using a `"variables"` object at the root level of the JSON
object.

