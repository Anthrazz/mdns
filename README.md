# Description

A command line tool to query multiple DNS resolver and show there delay and if they answer.

# Basic Usage

After build execute the binary with all DNS servers that you want to request and give optionally a domain with -d. Stop with CTRL+C. For example:

```
./go-mdnsping -d example.com 8.8.8.8 8.8.4.4 208.67.222.222 208.67.220.220 208.67.222.220 208.67.220.222 127.0.0.1
DNS Server     Success  Errors  Error %  Last  Average  Best  Worst - Queries
8.8.8.8        32       0       0.00%    4ms   4ms      3ms   16ms    ..............................
8.8.4.4        32       0       0.00%    4ms   4ms      3ms   11ms    ..............................
208.67.222.222 32       0       0.00%    3ms   4ms      3ms   8ms     ..............................
208.67.220.220 32       0       0.00%    4ms   4ms      3ms   7ms     ..............................
208.67.222.220 32       0       0.00%    4ms   4ms      3ms   5ms     ..............................
208.67.220.222 32       0       0.00%    4ms   4ms      3ms   8ms     ..............................
127.0.0.1      0        32      100.00%  0ms   0ms      0ms   7ms     ??????????????????????????????
```

The tool has a help when you call it without arguments:

```
./go-mdnsping
Usage: ./go-mdnsping  [-c <max count>] [-d <domain>] <dns resolver ip> [<dns resolver ip> ...]

This tool does query all given DNS servers and report the
answer delays and show a history of the last queries.

Arguments:
  -c count
        exit after sended count of DNS queries
  -d domain
        domain that should be queried (default "example.com")
  -h    show help
  -help
        show help
```

# How to Build

1. Install go
2. get this repo: `go get github.com/Anthrazz/go-mdnsping`
3. build it: `cd ~/go/src/github.com/Anthrazz/go-mdnsping && go build`
