kcbench
=======

```
Kernel compile benchmark script
Usage: kcbench [options]

Compiles a kernel and messures the time it takes

Available options:
 -d, --compiledir &lt;path&gt;      -- use &lt;path&gt;/kcbench for compile results (O=)
 -r, --detailedresults        -- print more detailed results
 -a, --ignore-running-apps    -- Do not warn if cron or other daemons run
 -i, --infinite               -- run endlessly
 -n, --iterations &lt;int&gt;       -- number or iterations
 -j, --jobs &lt;int&gt;             -- number of jobs to use ('make -j #') (*)
 -c, --no-cachefill           -- omit the initial kernel compile to fill caches
 -q, --quiet                  -- quiet
 -v, --verbose                -- increase verboselevel (*)
 -l, --savefailedlogs &lt;path&gt;  -- save log of failed compile runs in &lt;path&gt;
 -s, --src (&lt;path&gt;|&lt;version&gt;) -- take sources in &lt;path&gt; or from
                                 /usr/share/kcdata/linux-&lt;version&gt;

 -h, --help                   -- this text
 -V, --version                -- output program version

(*) -- option can be passed multiple times
```
