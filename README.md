
I'm one Java developer feeling very warm for Linux environments. Since I've started developing in Java I've noticed that my workstation/laptop tends to run out of memory quite often (well... it's all about java after all :) ) and I needed a tool to keep an eye on processes' sizes. And this is what I've come up with.



    ./processSizes -s 150
    Processes bigger than 150 MB:
    
    Total_shown:  -      -         8891.72MB  -
    Total_grand:  -      -         12453.1MB  -
    ---
    SUM(SIZE)     PID    USER      SIZE       COMMAND
    --->1GB---    14999  netikras  1785.11M   java
    --->3GB---    17489  netikras  1482.09M   chrome
    --->3GB---    2332   netikras  740.648M   cinnamon
    --->4GB---    17953  netikras  671.73M    chrome
    --->5GB---    1480   root      544.367M   Xorg
    --->5GB---    15217  netikras  544.246M   java
    --->6GB---    17577  netikras  522.984M   chrome
    --->6GB---    15252  netikras  496.941M   java
    --->7GB---    11596  netikras  494.57M    shutter
    --->7GB---    23110  netikras  364.25M    dropbox
    --->7GB---    22935  netikras  324.762M   soffice.bin
    --->8GB---    17703  netikras  256.352M   chrome
    --->8GB---    14099  netikras  174.828M   chrome
    --->8GB---    24646  netikras  165.246M   chrome
    --->8GB---    2349   netikras  163.938M   caribou
    --->8GB---    26092  netikras  159.652M   chrome


    ./processSizes -s 1000 -l 4
    Every 4,0s: gatherInfo 1000      Mon Dec 12 20:45:07 2016
    
    Processes bigger than 1000 MB:
    
    Total_shown:  -      -         3267.37MB  -
    Total_grand:  -      -         12464.2MB  -
    ---
    SUM(SIZE)     PID    USER      SIZE       COMMAND
    --->1GB---    14999  netikras  1785.11M   java
    --->3GB---    17489  netikras  1482.25M   chrome



Sizes are not calculated ideally, i.e. I do not pay any attention to shared memory and similar aspects, but it's still quite good for the job.

N.B. Script uses "column -t" to make this nice alignment and "-l" (or "loop") flag starts monitoring output with "watch" command. Keep that in mind when running on UNIX machines -- they tend to lack both: column and watch commands. Especially older ones.
