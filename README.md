kcbench
=======

**NOTE:** *This was forked from [`github.com/knurd/kcbench`](github.com/knurd/kcbench) which, in the meantime, has been deleted/brought offline.*

Kcbench is a simple benchmarking script that will compile a Linux kernel three times in a row and measure the time it takes. To give it a try simply run:

```
wget https://github.com/knurd/kcbench/raw/master/kcbench
bash kcbench
```

This will download and execute kcbench, which will do these things:

* download and extract a suitable linux kernel to ~/.cache/kcbench/
* create a temporary directory
* create a Linux kernel configuration in in using `make defconfig`
* three time in a row compile Linux using `make -j $(nproc --all) vmlinux`

In the end it will produce results that look like this:

```
Downloading source: This might take a while... Done.
Linux running:      4.19.0-0.rc1.git0.1.vanilla.knurd.1.fc28.x86_64 on x86_64 (foo.example.org)
Processor Cores:    4 -- Intel(R) Core(TM) i5-3350P CPU @ 3.10GHz
Compiler:           gcc (GCC) 8.1.1 20180712 (Red Hat 8.1.1-5)
Linux compiled:     4.14 (/home/thl/.cache/kcbench/linux-4.14)
Run 1 (-j 8):       3827 points  (e:261.30 sec  P:385% U:910.60 sec  S:97.84 sec)
Run 2 (-j 8):       3830 points  (e:261.05 sec  P:385% U:907.60 sec  S:99.76 sec)
Run 3 (-j 8):       3861 points  (e:258.98 sec  P:386% U:904.58 sec  S:96.61 sec)
```

Call "kcbench --help" to see the full potential of the benchmarking script:


```
Usage: kcbench [options]

Compiles a kernel and messures the time it takes

Available options:
 -d, --compiledir <path>      -- compile in <path>/kcbench (make 'O=#')
 -r, --detailedresults        -- print more detailed results
 -i, --infinite               -- run endlessly
 -n, --iterations <int>       -- number or iterations
 -j, --jobs <int>             -- number of jobs to use ('make -j #') (*)
 -q, --quiet                  -- quiet
 -v, --verbose                -- increase verboselevel (*)
 -s, --src (<path>|<version>) -- take sources in <path> or from either
                                 /usr/share/kcdata/linux-<version> or 
                                 ~/.cache/kcbench/linux-<version>; download
                                 ~/.cache/kcbench/linux-<version>; download
                                 them automatically if not found.
 -l, --savefailedlogs <path>  -- save log of failed compile runs in <path>
     --cachefill              -- omit results from initial compile
     --compiler (<exec>)      -- use compiler <exec> 
     --no-download            -- do not download sources automatically

 -h, --help                   -- this text
 -V, --version                -- output program version

(*) -- option can be passed multiple times
```
