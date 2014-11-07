Native ZFS for Linux!

ZFS is an advanced file system and volume manager which was originally
developed for Solaris and is now maintained by the Illumos community.

ZFS on Linux, which is also known as ZoL, is currently feature complete.  It
includes fully functional and stable SPA, DMU, ZVOL, and ZPL layers.

Full documentation for installing ZoL on your favorite Linux distribution can
be found at: <http://zfsonlinux.org>

in this fork, we try to jsonify the outputs of zfs commands (such as zfs list, zpool list)
To do this, we reuse some functions and are implementing the -J flag, we use a specific function display json (print_json) which takes charge two (char*)array, the one including the keywords, the other values.

json would offer the standardization of zfs output's  entirety and thus be able to script some operation ...

one exemple of zfs list output :

the standard :

```
zfs list
NAME         USED  AVAIL  REFER  MOUNTPOINT
tank        7,66M  1,48G    29K  /tank
tank/test   1,25M  1,48G    16K  -
tank/test1  1,25M  1,48G    16K  -
tank/test2  1,25M  1,48G    16K  -
tank/test3  1,25M  1,48G    16K  -
tank/test4  1,25M  1,48G    16K  -
tank/test5  1,25M  1,48G    16K  -
```

the json output :

```json
{"cmd" : "zfs list","output:" : [{"name" : "tank", "used" : "8035328", "available" : "1585800192", "referenced" : "29696", "mountpoint" : "/tank"},{"name" : "tank/test", "used" : "1310720", "available" : "1587094528", "referenced" : "16384", "mountpoint" : "-"},{"name" : "tank/test1", "used" : "1310720", "available" : "1587094528", "referenced" : "16384", "mountpoint" : "-"},{"name" : "tank/test2", "used" : "1310720", "available" : "1587094528", "referenced" : "16384", "mountpoint" : "-"},{"name" : "tank/test3", "used" : "1310720", "available" : "1587094528", "referenced" : "16384", "mountpoint" : "-"},{"name" : "tank/test4", "used" : "1310720", "available" : "1587094528", "referenced" : "16384", "mountpoint" : "-"},{"name" : "tank/test5", "used" : "1310720", "available" : "1587094528", "referenced" : "16384", "mountpoint" : "-"}]}
```
