# Tahoe-LAFS with I2P Support

[Tahoe-LAFS][tahoe] with I2P support.

## Building

    docker build -t geti2p/tahoe-lafs .

## Running

### Set up

When you run, please make sure that you have enabled [SAM][sam] in I2P.

The following commands will set up the configs, and download a bunch of I2P introducers.

    $ cd somedir
    $ docker run --net="host" -v $(pwd):/root/.tahoe/:rw geti2p/tahoe-lafs tahoe create-node --nickname=idonteditconfigs --hide-ip --introducer=pb://exupps5kk3amc5iq4q6f5ahggkm4s5fl@i2p:oj7cffq5fnk46iw3i3h2sdgncxrqbxm7wh6i4h2cbpmqsydygkcq.b32.i2p/introducer --listen=i2p --i2p-sam-port=tcp:127.0.0.1:7656
	$ wget -O ./private/introducers.yaml https://gist.githubusercontent.com/chris-barry/54c7c5964deac911c5acc55f570bb1af/raw/45c84ab8ed4426c36f2a48b90aca0f3083f90dd9/introducers.yaml

### Actually Running

Note that this runs in host mode. This isn't generally needed, but it makes it easier for most users.

    $ docker run geti2p/tahoe-lafs:latest -p 3456:3456 -v $(pwd):/root/.tahoe:rw --net="host"

## License

Same license as Tahoe-LAFS -- [GPL2+][gpl] / [TGPPL][tgppl]

[tahoe]: https://tahoe-lafs.org/
[sam]: http://127.0.0.1:7657/configclients
[gpl]: https://github.com/tahoe-lafs/tahoe-lafs/blob/master/COPYING.GPL
[tgppl]: https://github.com/tahoe-lafs/tahoe-lafs/blob/master/COPYING.TGPPL.rst
