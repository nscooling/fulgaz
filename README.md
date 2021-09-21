# fulgaz

Note these video files can be very large, form the [FUlGaz support site](https://support.fulgaz.com/hc/en-us/articles/360058353752-Ride-videos-are-not-downloading-or-taking-too-long):
```
- Ensure there is more than enough free space on your device for the video file. As a general guide, an hour of FulGaz video in each quality setting is roughly...

4K = 10GB
1080p = 2GB
720p = Under 1GB
```

For example, in the samllest file size, 720P, here a sample of file sizes:
```
1.2G - Col-de-Ichere-and-Col-de-Lie.mp4
383M - Col-de-Jambaz.mp4
686M - Col-de-la-Croix-Blanche.mp4
1.2G - Col-de-la-Joux-Plane.mp4
712M - Col-de-la-Ramaz-East.mp4
1.0G - Col-de-la-Ramaz-West.mp4
1.1G - Col-du-Marie-Blanque-from-Louvie-Juzon.mp4
2.0G - Col-du-Tourmalet-from-Saint-Sauveur.mp4
1.9G - Col_Agnel.mp4
1.3G - Col_de_Vars.mp4
977M - Col_du_Glandon.mp4
1.9G - Colle_Delle_Finestre.mp4
1.7G - Inkpen-Hill.mp4
930M - LB-Galibier.mp4
2.4G - LB-col-de-la-madeleine.mp4
2.4G - LBVentoux.mp4
1.7G - col-d-izoard-19.mp4
1.7G - col-d-liseran.mp4
1.2G - col-d-ornon.mp4
788M - col-de-aravis.mp4
882M - col-de-braus.mp4
2.4G - col-de-la-bonette.mp4
1.2G - col-de-la-madone.mp4
1.4G - col-de-la-morte.mp4
1.3G - col-de-sarenne.mp4
1.4G - col-de-turini.mp4
1.6G - col-de-vars.mp4
1.1G - col-du-chaussy.mp4
2.1G - col-du-galibier.mp4
1.3G - col-du-telegraphe.mp4
2.2G - colle-dell-agnello.mp4
1.3G - como-to-bellagio.mp4
```

LB-Galibier.mp4 is [Col du Galibier from Col du Lautare](https://fulgaz.com/fulgaz-rides/?fg_ride=ad6ce13c35fd489767031f29). The ride time is 47mins with a filesize of 930Mb.

## Linux/macOS

### Download an individual file

You can use the [FulGaz member website](https://members.fulgaz.com/downloads) to download individual files.

Alternatively they can be downloaded from the command line using `wget`.

```
$ wget -N <web address>
```
For example, to download [Col du Galibier](https://fulgaz.com/fulgaz-rides/?fg_ride=a3a6f662cd52011d977eb1d9) using northern approach from Valloire, you would do
```
$ wget -N https://fulgaz.cachefly.net/file/fulgaz-videos/720P/col-du-galibier.mp4
```

The `-N` will only download the file if you don't already have it stored or there has been an update to the file.

The only downbside is you do have to link the MP4 filename to the ride. In most cases this is obvious, but where there are multiple rides, this is can be a bit of trial and error.

### Downloading all ride files

** WARNING ** 
This will take up a long time (maybe days depending on you bandwidth) and requite *A LOT* of disk space (think > 4TB)

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

If you don't want to suck up all you bandwidth (and keep the rest of the household happy) then add `--limit-rate=500k`

e.g.
```
$ wget -N -b -limit-rate=500k -i fulgaz-list-<size>.txt
```


### Downloading a subset of files

To copy just a subset, create a copy of the main file (based on format) and remove the ones you don't want, e.g.
```
$ cp <main-file> <new-file>
```

```
$ cp fulgaz-list-720P.txt fulgaz-my-list.txt
```

Edit that file (macOS)
```
$ open fulgaz-my-list.txt
```
and then use that as the download file
```
$ wget -N -b -i fulgaz-my-list.txt
```

At any time you can add to this file and just run again. 

Using the `-N` means the ones already downloaded won't get redownloaded.

