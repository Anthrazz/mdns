# Description

A command line tool to query multiple DNS resolver and show there delay and if they answer.

# Basic Usage

After build execute the binary with all DNS servers that you want to request and the wanted domain as last argumemt. Stop with CTRL+C. For example:

```
./go-mdnsping 8.8.8.8 8.8.4.4 208.67.222.222 208.67.220.220 208.67.222.220 208.67.220.222 127.0.0.1 example.com
DNS Server     Count Last Average Best Worst - Queries
8.8.8.8        32    3ms  4ms     3ms  8ms     ..............................
8.8.4.4        32    4ms  4ms     3ms  8ms     ..............................
208.67.222.222 32    4ms  4ms     3ms  8ms     ..............................
208.67.220.220 32    4ms  4ms     3ms  8ms     ..............................
208.67.222.220 32    3ms  4ms     3ms  7ms     ..............................
208.67.220.222 32    4ms  4ms     3ms  7ms     ..............................
127.0.0.1      32    1ms  0ms     0ms  5ms     ??????????????????????????????
```

The tool has a help when you call it without arguments:

```
./go-mdnsping
Usage: ./go-mdnsping <dns server ip> [<dns server ip> ...] [<domain>]

This tool does query all given DNS servers and report the
answer delays and show a history of the last queries.

Arguments:
        <dns server ip> : IPs of DNS servers that should be queried.
        <domain>        : which domain should be queried? Default is 'google.de'. Must be last.
```
