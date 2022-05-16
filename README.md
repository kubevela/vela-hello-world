# Hello World

This is a simple Docker image that just gives http responses on port 8000. It's
small enough to fit on one floppy disk:

```bash
$ docker images | grep hello-vela
oamdev/hello-vela     latest    453425b45a21   3 minutes ago   1.24MB
```

This is forked from https://github.com/crccheck/docker-hello-world.

## Sample Usage

### Starting a web server on port 80

```bash
$ docker run -d --rm --name web-test -p 80:8000 oamdev/hello-vela
```

You can now interact with this as if it were a dumb web server:

```
$ curl localhost
<pre>
Hello KubeVela! Make shipping applications more enjoyable.


                                   ,
                                   //,
                                   ////
                               ./  /////*
                             ,///  ///////
                           ./////  ////////
                          ///////  /////////
                         ////////  //////////
                       ,/////////  ///////////
                      ,//////////  ///////////.
                     .///////////  ////////////
                     ////////////  ////////////.
                    *////////////  ////////////*
       #@@@@@@@@@@@*     ..,,***/  /////////////
        /@@@@@@@@@@@#
         *@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@&
          .@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@.

              @@@@@@@@@@@@@@@@@@@@@@@@@@@@@
                .&@@@*    *@@@&    ,@@@&.

       _  __       _          __     __     _
      | |/ /_   _ | |__    ___\ \   / /___ | |  __ _
      | ' /| | | || '_ \  / _ \\ \ / // _ \| | / _` |
      | . \| |_| || |_) ||  __/ \ V /|  __/| || (_| |
      |_|\_\\__,_||_.__/  \___|  \_/  \___||_| \__,_|
</pre>
```

```
$ curl -I localhost
HTTP/1.0 200 OK
```

```
$ curl -X POST localhost/super/secret
<HTML><HEAD><TITLE>501 Not Implemented</TITLE></HEAD>
...snip...
```

```
$ curl --write-out %{http_code} --silent --output /dev/null localhost
200
```
