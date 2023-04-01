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

1. profiling target process till the end:
   ```console
   # hw_perf -- target_process
   ```
1. profiling `WindowServer` for a 5 seconds:
   ```console
   # hw_perf -p `pgrep WindowServer` -- sleep 1
   loaded db: icelake (Intel Ice Lake)
   number of fixed counters: 4
   number of configurable counters: 8
   CPU tick frequency: 1000000000
   ------------------------
   thread: 2429, trace time: 0.630195
           cycles: 814049
     instructions: 365807
         branches: 74623
    branch-misses: 5543
   ------------------------
   thread: 2286, trace time: 0.503226
           cycles: 914995
     instructions: 490641
         branches: 95029
    branch-misses: 5540
   ------------------------
   thread: 876, trace time: 0.249070
           cycles: 3266042
     instructions: 1441126
         branches: 302765
    branch-misses: 17036
   ------------------------
   thread: 100314, trace time: 0.677631
           cycles: 1196237
     instructions: 466107
         branches: 92569
    branch-misses: 8515
   ------------------------
   thread: 100544, trace time: 0.117212
           cycles: 532075
     instructions: 227263
         branches: 46883
    branch-misses: 3568
   ------------------------
   thread: 100315, trace time: 0.116617
           cycles: 355016
     instructions: 111331
         branches: 21964
    branch-misses: 2261
   ------------------------
   thread: 100147, trace time: 0.639521
           cycles: 3401671
     instructions: 1482879
         branches: 331368
    branch-misses: 23751
   ------------------------
   all threads:
           cycles: 10480085
     instructions: 4585154
         branches: 965201
    branch-misses: 66214
   ```
