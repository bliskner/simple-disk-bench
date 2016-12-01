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
./disk-bench device [threadcount] ["destructive"]
```

## sample output
```
root@mylinuxhost ~ # ./disk-bench /dev/vg/san-volume 1
running simple disk bench
download and contribute here -> https://github.com/bliskner/simple-disk-bench

Benchmarking /dev/vg/san-volume [7077888 blocks, 28991029248 bytes, 27 GB, 27648 MB, 28 GiB, 28991 MiB]
[512 logical sector size, 512 physical sector size]
[running 1 reading thread using a blocksize of 4096 byte]
Wait 30 seconds..............................
Result: 1523 reads per second, 0.186 ms random access time (226732 < offsets < 28990763568)
```
