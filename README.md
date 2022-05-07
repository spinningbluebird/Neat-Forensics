# Neat-Forensics
Just some neat forensics tricks
don't look yet she's naked D:

Y'all Like Tricks?

VOLATILITY FORENSICS

Dumping Passwords with Volatility
```
./vol.py -f file.dmp windows.hashdump.Hashdump #Grab common windows hashes (SAM+SYSTEM)
./vol.py -f file.dmp windows.cachedump.Cachedump #Grab domain cache hashes inside the registry
./vol.py -f file.dmp windows.lsadump.Lsadump #Grab lsa secrets
```

Dumping Clipboard
```
volatility --profile=Win7SP1x86_23418 iehistory -f file.dmp
```

Dumping Internet History :D
```
volatility --profile=Win7SP1x86_23418 iehistory -f file.dmp
```

Command Line History
```
python3 vol.py -f file.dmp windows.cmdline.CmdLine #Display process command-line arguments
volatility --profile=PROFILE cmdline -f file.dmp #Display process command-line arguments
volatility --profile=PROFILE consoles -f file.dmp #command history by scanning for _CONSOLE_INFORMATION
```


BULK_EXTRACTOR FORENSICS
Finding TOR Activity
```
bulk_extractor -o output example.vmem
cat url.txt | grep "onion" | awk '{print $2}' | sort | uniq -c | sort -nr
```



