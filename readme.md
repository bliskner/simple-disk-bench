# disk-bench

disk-bench.c is a simple programm to test multithreaded io requests to a linux disk volume

- initialy developed by http://linuxinsight.com/how_fast_is_your_disk.html
- multithreading support added by https://github.com/meebey/meebey-web/blob/master/research/seeker_baryluk.c (at least i've taken the source from here)
- added write support

## features:
- easy to use, understand and modify
- read and write support
- single threaded to multithreaded IO

## how to compile

```
gcc -o disk-bench -O2 -march=native disk-bench.c -pthread
```

## usage

specifying the destructive option will execute a write test without asking,
destroying the data on the specified volume

```
./disk-bench device [threads] ["destructive"]
```

## sample output
```
root@mylinuxhost ~ # ./disk-bench /dev/hdd/san-volume 1
Benchmarking /dev/hdd/san-volume [26214400 blocks, 107374182400 bytes, 100 GB, 102400 MB, 107 GiB, 107374 MiB]
[512 logical sector size, 512 physical sector size]
[1 threads]
running in read mode
Wait 30 seconds..............................
Result: 3332 reads/writes per second, 0.300 ms random access time (2030650 < offsets < 107371362650)
```
