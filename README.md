vdr-epg-tool
============

XMLTV EPG VDR loader tool

Loads XMLTV (xmltv.org) output into VDR's EPG ([electronic program guide](http://en.wikipedia.org/wiki/Electronic_program_guide)). Almost
a straight port of [xmltv2vdr.pl](https://github.com/rdaoc/xmltv2vdr/blob/master/xmltv2vdr.pl) into Go.

Features over xmltv2vdr.pl:

* No need to modify VDR's channel.conf to add the XMLTV Id !!
* No external dependencies once static binary built
* XML parser not based on regular expressions
* No genre, rating, etc files needed

tv_grab_na_dd --days 1 --output /tmp/epg_schedules_direct.xml \
&& vdr-epg-tool -c /var/lib/vdr/channels.conf -x
/tmp/epg_schedules_direct.xml epg-load \
&& rm /tmp/epg_schedules_direct.xml
