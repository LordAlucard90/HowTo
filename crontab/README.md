# Crontab

## Show cron jobs
```bash
$ crontab -l          # current user
$ crontab -u user -l  # specific user
$ sudo crontab -l     # super user
```

## Edit user cron jobs
```bash
$ crontab -e          # current user
$ crontab -u user -e  # specific user
$ sudo crontab -e     # super user
```

## Delete all user cron jobs
```bash
$ crontab -r          # current user
$ crontab -u user -r  # specific user
$ sudo crontab -r     # super user
```

### Schedule cron jobs

#### Sintax
`<minute> <hour> <day of month> <month> <day of week> <command>`

##### Where:
- `<minute> <hour> <day of month> <month> <day of week>` could be:

  - `*` means every value of that type.

  - `<n1>-<n2>` means every value from n1-th to n2-th included.

  - `<n1>,<n2>` means n1-th and n2-th.

  - `<n1>-<n2>,<n3>-<n4>` means every value from n1-th to n2-th and every value from n2-th to n3-th.

  - `<n1>-<n2>/<step>` means the n1-th, the (n1+step)-th, the (n1+2*step)-th and so on until (n1+k*step) <= n2.

  - `*/<step>` is like `<n1>-<n2>/<step>` in the range of all values of that type.

- `<command>`

  is a bash inline command.


#### Configuration examples
- **Every Minute**

  ```* * * * * <command>```

- **Every 5 Minutes**

  ```*/5 * * * * <command>```

- **Every Hour**

  ```0 * * * * <command>```

- **Every Hour at Minute 15**

  ```15 * * * * <command>```

- **Every 2 Hours**

  ```* */2 * * * <command>```

- **Every Day**

  ```0 0 * * * <command>```

- **Every Day at 3am**

  ```0 3 * * * <command>```

- **Every Sunday**

  ```0 0 * * 0 <command>``` or ```0 0 * * SUN <command>```

- **Every Working Day**

  ```0 0 * * 1-5 <command>```

- **Every Month**

  ```0 0 1 * * <command>```

- **Every First Day of Month at 15:30**

  ```30 15 1 * * <command>```

- **Every 6 Months**

  ```0 0 1 */6 * <command>```

- **Every Year**

  ```0 0 1 1 * <command>```

## Shortcuts

### Sintax
`<shortcut> <command>`

#### Shortcuts' List:
- **@rebot** run once at startup
- **@yearly** run once a year
- **@monthly** run once a month
- **@weekly** run once a week
- **@daily** run once a day
- **@hourly** run once an hour
