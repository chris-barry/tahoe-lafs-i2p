# Tahoe-LAFS with I2P Support

[Tahoe-LAFS][tahoe] with I2P support.

## Building

    docker build -t geti2p/tahoe-lafs .

## Running

When you run, please make sure that you have enabled [SAM][sam] in I2P.

Also, please note that this runs in host mode.
This isn't generally needed, but it makes it easier for most users.

    docker run geti2p/tahoe-lafs:latest -p 3456:3456 -v data-directory:/root/.tahoe:rw --net="host"

## Post Install

This is a filler section.
Don't trust it yet!

TODO: make this multi introducer / make sure it works.

    docker exec $(docker ps --filter="name=barryim_tahoe-lafs" --format="{{.ID}}") tahoe create-node --nickname=bleg --hide-ip --introducer=pb://exupps5kk3amc5iq4q6f5ahggkm4s5fl@i2p:oj7cffq5fnk46iw3i3h2sdgncxrqbxm7wh6i4h2cbpmqsydygkcq.b32.i2p/introducer --listen=i2p --i2p-sam-port=tcp:127.0.0.1:7656

## License

Same license as Tahoe-LAFS -- [GPL2+][gpl] / [TGPPL][tgppl]

[tahoe]: https://tahoe-lafs.org/
[sam]: http://127.0.0.1:7657/configclients
[gpl]: https://github.com/tahoe-lafs/tahoe-lafs/blob/master/COPYING.GPL
[tgppl]: https://github.com/tahoe-lafs/tahoe-lafs/blob/master/COPYING.TGPPL.rst
