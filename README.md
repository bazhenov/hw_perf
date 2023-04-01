# hw_perf

macOS hardware CPU counter profiler. Analog of a `perf stat` from Linux. Based on a [prototype](https://gist.github.com/ibireme/173517c208c7dc333ba962c1f0d67d12) created by [YaoYuan](https://github.com/ibireme).

# Building from source

```console
$ git clone https://github.com/bazhenov/hw_perf
$ cd hw_perf
$ make
```

# Usage

Tracing requires root privileges.

1. profiling target process till the end
   ```console
   # hw_perf -- target_process
   ```
1. profiling existing pid for a given amount of time (in seconds)
   ```console
   # hw_perf -p `pgrep my-process` -t 5
   ```
