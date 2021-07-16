```shell
$ git clone https://github.com/raysan5/raylib-game-template.git
$ cd raylib-game-template/src
$ git clone https://github.com/corelight/cwrap
$ sed -Ei s|^CC = gcc|CC = ./cwrap/cwrap.pl| Makefile
$ sed -Ei "s|find . -type f|find . -type f ! -path './cwrap/*'|" Makefile
$ make BUILD_MODE=DEBUG
$ CWRAP_LOG_FILE=1 CWRAP_LOG_NUM=1 CWRAP_LOG_TIMESTAMP=1 CWRAP_LOG_THREAD_ID=1 CWRAP_LOG_CURT=1 CWRAP_LOG_VERBOSITY_SET=1 gdb ./raylib_game
```

In gdb you can do something like this:
```shell
(gdb) b main
(gdb) run
(gdb) continue
```

```shell
$ tail -f cwrap.out
$ make clean
```
