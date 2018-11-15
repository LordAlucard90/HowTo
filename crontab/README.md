# Crontab

## Edit user crontabs
```bash
$ crontab -e      # current user
$ sudo crontab -e # super user
```

## Show crontabs
```bash
$ crontab -l      # current user
$ sudo crontab -l # super user
```

## Scheduling crontabs

### Sintax
`
<minute> <hour> <day of month> <month> <day of week> <command>
`

#### Where:
- `<minute> <hour> <day of month> <month> <day of week>` could be:

  - `*` means every value of that type.

  - `<n1>-<n2>` means every value from n1-th to n2-th included.

  - `<n1>,<n2>` means n1-th and n2-th.

  - `<n1>-<n2>,<n3>-<n4>` means every value from n1-th to n2-th and every value from n2-th to n3-th.

  - `<n1>-<n2>/<step>` means the n1-th, the (n1+step)-th, the (n1+2*step)-th and so on until (n1+k*step) <= n2.

  - `*/<step>` is like `<n1>-<n2>/<step>` in the range of all values of that type.

- `<command>`

  is a bash inline command.


### Configuration examples
- **Every Minute**

  ```* * * * * command```

- **Every 5 Minute**

  ```*/5 * * * * command```
