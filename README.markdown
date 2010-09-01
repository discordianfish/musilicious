# musilicious

This is a web based client for the [music player daemon][mpd] (mpd), powered by [mojolicious][mojo].

## Status
...should not be used by anyone. Totaly broken.


## Features

* ajax jquery web 2.0 dynamic on demand bullshit bingo capable
* static, good old plain html
* -> Should work fine on lynx and look porno on your fancy new laptop
* supports basic mpd features like controling, editing playlist, setting outputs

## Requirements

* Mojolicious
* Audio::MPD

atm you need to fetch jquery-ui extract it to `public/static`.
I'll bundle that some time.


## Using it

Simple:

    ./musilicious daemon

Go to http://whatever:3000 and have fun

You can use environment vars if your mpd host isn't localhost

    MPD_HOST=whereever MPD_PORT=123 ./musilicious daemon

But you can deploy it as all mojolicious apps, this is my setup for lighttpd:

    fastcgi.server = (
        "/music" => ((
            "socket"   => "/tmp/music.fcgi.socket",
            "check-local" => "disable",
            "broken-scriptfilename" => "enable",
            "max-procs" => 1,
            "docroot" => "/",
            "bin-path" => "/data/git/musilicious/musilicious fastcgi",
        ))
    )

[mpd]: http://musicpd.org/
[mojo]: http://mojolicious.org/

