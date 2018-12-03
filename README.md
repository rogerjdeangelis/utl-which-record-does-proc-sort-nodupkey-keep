# utl-which-record-does-proc-sort-nodupkey-keep
Which record does 'proc sort nodupkey equals' keep
    Which record does 'proc sort nodupkey equals' keep

    You need the default option equals. Equals maintains the order of the input.

    github
    https://tinyurl.com/ydaca3et
    https://github.com/rogerjdeangelis/utl-which-record-does-proc-sort-nodupkey-keep

    https://tinyurl.com/yaud5eh2
    https://stackoverflow.com/questions/53562723/sas-proc-sort-nodupkey-keeping-the-wrong-record


    INPUT
    =====

     WORK.HAVE total obs=12

                 |  RULES  (keeps first.id )
     ID    VAL   |
                 |
      1     A    | =>  Keep this one
      1     B    |
      1     C    |
      1     D    |
                 |
      2     3    | =>  Keep this one
      2     2    |
      2     1    |
      2     0    |
                 |
      3     1    | =>  Keep this one
      3     1    |
      3     9    |
      3     3    |


    PROCESS
    =======

    proc sort data=have out=havUnq EQUALS nodupkey;
    by id;
    run;quit;


    OUTPUT
    =====

    WORK.HAVUNQ total obs=3

     ID    VAL

      1     A
      2     3
      3     1

    *                _              _       _
     _ __ ___   __ _| | _____    __| | __ _| |_ __ _
    | '_ ` _ \ / _` | |/ / _ \  / _` |/ _` | __/ _` |
    | | | | | | (_| |   <  __/ | (_| | (_| | || (_| |
    |_| |_| |_|\__,_|_|\_\___|  \__,_|\__,_|\__\__,_|

    ;

    data have;
    input id val$;
    cards4;
    1 A
    1 B
    1 C
    1 D
    2 3
    2 2
    2 1
    2 0
    3 1
    3 1
    3 9
    3 3
    ;;;;
    run;quit;



