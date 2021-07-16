```shell
$ cd src
$ git clone https://github.com/corelight/cwrap
$ sed -E s|$CC = gcc|CC = ./cwrap/cwrap.pl| Makefile
$ sed -E s|find . -type f|find . -type f ! -path './cwrap/*'| Makefile
$ make clean
$ make BUILD_MODE=DEBUG
$ CWRAP_LOG_FILE=1 CWRAP_LOG_NUM=1 CWRAP_LOG_TIMESTAMP=1 CWRAP_LOG_THREAD_ID=1 CWRAP_LOG_CURT=1 CWRAP_LOG_VERBOSITY_SET=1 gdb ./raylib_game
```
