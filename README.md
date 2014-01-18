kcbench
=======

```
Kernel compile benchmark script
Usage: kcbench [options]

Compiles a kernel and messures the time it takes

Available options:
 -d, --compiledir <path>      -- use <path>/kcbench for compile results (O=)
 -r, --detailedresults        -- print more detailed results
 -a, --ignore-running-apps    -- Do not warn if cron or other daemons run
 -i, --infinite               -- run endlessly
 -n, --iterations <int>       -- number or iterations
 -j, --jobs <int>             -- number of jobs to use ('make -j #') (*)
 -c, --no-cachefill           -- omit the initial kernel compile to fill caches
 -q, --quiet                  -- quiet
 -v, --verbose                -- increase verboselevel (*)
 -l, --savefailedlogs <path>  -- save log of failed compile runs in <path>
 -s, --src (<path>|<version>) -- take sources in <path> or from
                                 /usr/share/kcdata/linux-<version>

 -h, --help                   -- this text
 -V, --version                -- output program version

(*) -- option can be passed multiple times
```
