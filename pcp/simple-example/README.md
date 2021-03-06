# simple-example of pcp

## compile + run

    $ make
    gcc -o pcptest -lpcp_import -lpcp pcptest.c
    $ ./pcptest
    $

## dump log contents

    $ pmdumplog -a mover_v1
    Log Label (Log Format Version 2)
    Performance metrics from host centos
        commencing Mon Jan 21 22:19:15.070051 2019
        ending     Mon Jan 21 22:19:19.072440 2019
    Archive timezone: GMT
    PID for pmlogger: 4058
    
    Descriptions for Metrics in the Log ...
    PMID: 245.0.1 (mover.nfile)
        Data Type: 32-bit unsigned int  InDom: PM_INDOM_NULL 0xffffffff
        Semantics: instant  Units: count
    
    Instance Domains in the Log ...
    
    Temporal Index
                    Log Vol    end(meta)     end(log)
    22:19:15.070051       0          132          132
    22:19:15.070051       0          183          132
    22:19:19.072440       0          183          332
    
    [40 bytes]
    22:19:15.070051 1 metric
        245.0.1 (mover.nfile): value 123
    
    [40 bytes]
    22:19:16.071193 1 metric
        245.0.1 (mover.nfile): value 123
    
    [40 bytes]
    22:19:17.071592 1 metric
        245.0.1 (mover.nfile): value 123
    
    [40 bytes]
    22:19:18.071924 1 metric
        245.0.1 (mover.nfile): value 123
    
    [40 bytes]
    22:19:19.072440 1 metric
        245.0.1 (mover.nfile): value 123
    $

## display log contents

    $ pmrep -p -a mover_v1 mover.nfile
              m.nfile
                count
    07:31:17      123
    07:31:18      123
    07:31:19      123
    07:31:20      123
    07:31:21      123
    $

## display log in CSV format

    $ pmrep -p -o csv -a mover_v1 mover.nfile
    Time,"mover.nfile"
    2019-01-22 07:31:17,123
    2019-01-22 07:31:18,123
    2019-01-22 07:31:19,123
    2019-01-22 07:31:20,123
    2019-01-22 07:31:21,123
    $

