A 'time'-like utility for Unix that measures peak memory usage.

Works in both interactive and non-interactive environments.

Usage:

```bash
usage: memusg [-h] [-o OUTPUT_TO_FILE] [-t] [-p POLL_INTERVAL]
              [-w WRITE_INTERVAL] [-H] [-s]
              ...

positional arguments:
  args

optional arguments:
  -h, --help            show this help message and exit
  -o OUTPUT_TO_FILE, --output-to-file OUTPUT_TO_FILE
                        Output usage to file
  -t, --time            Output run time of subprocess as well
  -p POLL_INTERVAL, --poll-interval POLL_INTERVAL
                        Polling interval in seconds to check for current
                        memory usage
  -w WRITE_INTERVAL, --write-interval WRITE_INTERVAL
                        Interval in seconds to write current peak usage to
                        stdout while process is running (Disable using 0)
  -H, --no-humanize     No humanization of the value of time (second) and
                        memory (KB) usage
  -s, --shell           execute through shell, useful for multiple cmmands and
                        commands with pipes
```

```bash
export PATH=$path_to_memusg:$PATH
memusg my_command
```

Example:

```bash
$ memusg -t sleep 2

elapsed time: 2.039s
peak rss: 664.0 KB

$ memusg -t -s "echo 1 | cat"
1

elapsed time: 0.110s
peak rss: 0B

```
