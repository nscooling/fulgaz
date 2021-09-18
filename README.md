# fulgaz

## Linux/macOS

To download all video files
```
$ wget -N -b -i fulgaz-list-<size>.txt
```
* `-N` will only download any new or changed files
* `-b` dos it in the background

e.g. in 4K
```
$ wget -N -b -i fulgaz-list-4K.txt
```

If you don't want to suck up sll you bandwidth (and keep the rest of the household happy) then add `--limit-rate=500k`

e.g.
```
$ wget -N -b -limit-rate=500k -i fulgaz-list-<size>.txt
```