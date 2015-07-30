# sparometer
Spar'o'meter and NZR Standby Energy Monitor SEM 16+ USB data read out

First run after git clone:
==========================
* git clone https://github.com/hanschou/sparometer
* aclocal ; autoconf ; autoheader ; automake --add-missing
* ./configure
* make
* sudo make install
* sparometer # to see the help
* sparometer --set-{time,date,interval=01*min,text=mydevice}
* sparometer --get-sample-effect # see current Watt use
* sparometer --start-log
* sleep 120 # "get-logdata" gives an error if no data found
* sparometer --get-logdata
* msparometer # batch download at reformat data
* sparometer --reset-log # stop logging and clear data

Clean up:
=========
rm -rf $( ls | grep -Ev "(ChangeLog|configure.ac|LICENSE|Makefile.am|msparometer|README|README.md|sparometer.c)" )
