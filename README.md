# bleu-champ

    mkdir build
    cd build
    cmake ..
    make
    
    ./bin/bleu-champ -s ... -t ...

```
Usage: ./bin/bleu-champ [options]
Allowed options:

General options:
  -s [ --source ] arg                   Source language file, used for 
                                        alignment computation
  -t [ --target ] arg                   Target language file, used for 
                                        alignment computation
  -h [ --help ]                         Print this help message and exit
  -q [ --quiet ]                        Do not print anything to stderr

Alignment algorithm options:
  -w [ --width ] arg (=10)              Width of search corridor around 1-1 
                                        path
  --skip-1st                            Skip 1st pass. Can be very slow for 
                                        larger files
  --skip-2nd                            Skip 2nd pass and output only 1-1 path

Output options:
  -l [ --ladder ]                       Output in hunalign ladder format (not 
                                        affected by other printing options)
  -S [ --Source ] arg                   Substitute source language file, used 
                                        only for output in text mode. Has to be
                                        sentence aligned with --source  arg
  -T [ --Target ] arg                   Substitute target language file, used 
                                        only for output in text mode. Has to be
                                        sentence aligned with --target  arg
  -m [ --min-score ] arg (=-3.40282347e+38)
                                        Print rungs with scores of at least  
                                        arg
  -b [ --print-beads ]                  Print column with beads
  -i [ --print-ids ]                    Print column with sentence ids
  -p [ --print-scores ]                 Print column with scores
  -1 [ --print-1-1 ]                    Print only 1-1 rungs
  -u [ --print-unaligned ]              Print unaligned sentences
```
