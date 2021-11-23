# XLED-SHELL - unofficial control of Twinkly - Smart Decoration LED lights

XLED is a set of bash (shell) scripts to control
[Twinkly](https://www.twinkly.com/) - Smart Decoration LED lights for
Christmas.

Official materials says:

    Twinkly is a LED light device that you can control via smartphone. It
    allows you to play with colouful and animated effects, or create new ones.
    Decoration lights, not suitable for household illumination.

Since its [Kickstarter
project](https://www.kickstarter.com/projects/twinkly/twinkly-smart-decoration-for-your-christmas)
in 2016 many products were introduced with varying properties and features.
Most notably products released since September 2019 are identified as
Generation II. Older products are since then referred as Generation I.

This is free software available under MIT license.

Depends on following binaries:

* `bash` version 4 or higher
* `head` and `base64` - usually part of coreutils package
* `jq`

Firmware version-aware script that queries most of known endpoints from
[unofficial documentation](https://xled-docs.readthedocs.io) and writes whole
endpoint paths in otput:

.. code-block:: console

    $ ./all 192.168.4.1

Wrapper of previous script that also writes output to filename that consists of
device name and firmware version:

.. code-block:: console

    $ ./gather 192.168.4.1

Example of high level wrapper:

.. code-block:: console

    $ ./set-demo 192.168.4.1

Another example 

.. code-block:: console

    $ echo -e 'Hello!' | ./set-echo 192.168.4.1

which requires `awk` to escape newlines. Other control characters from U+0000
through U+001F are not escaped and `jq` complains.

Example of low level get where second argument is an endpoint without
`/xled/v1/` prefix:

.. code-block:: console

    $ ./get 192.168.4.1 gestalt

If standard output (stdout) of a script is associated with a terminal or if it
is run with environment variable `XLED_DEBUG=1`, scripts shows more verbose
output on standard error output (stderr) and runs `jq` to pretty format output.
Run with `XLED_DEBUG=0` to get only response from the device.

All shell scripts are expected to be run from current directory because they
sometimes they run other scripts and expects them in the same directory.

## Why?

This is a quick way to test Twinkly API.

### References

There are other projects that might be more suitable for your needs:

* [Python library and CLI](https://github.com/scrool/xled)
* [Twinkly integration in Home Assistant](https://www.home-assistant.io/integrations/twinkly/)
* SmartThings:

  * [Twinkly integration in SmartThings by StevenJonSmith](https://github.com/StevenJonSmith/SmartThings)
  * [Twinkly integration in SmartThings by Dameon87](https://github.com/Dameon87/SmartThings)

* [TwinklyTree Binding](https://github.com/mvanhulsentop/openhab-addons/tree/twinklytree/bundles/org.openhab.binding.twinklytree) for openHAB

* [Twinkly HomeKit Hub for Mongoose OS](https://github.com/d4rkmen/twinkly-homekit) using [Twinkly library for Mongoose OS](https://github.com/d4rkmen/twinkly)

* [TwinklyWPF](https://github.com/MarkAlanJones/TwinklyWPF) - .net 5 GUI and API library
* [ioBroker.twinkly](https://www.npmjs.com/package/iobroker.twinkly) - twinkly adapter for ioBroker to communicate with the Twinkly lights
* [Twinkly.vb for HomeSeer](https://forums.homeseer.com/forum/developer-support/scripts-plug-ins-development-and-libraries/script-plug-in-library/1348314-twinkly-vb-christmas-tree-lights-with-predefined-and-custom-animations)
* [thingzi-logic-twinkly](https://www.npmjs.com/package/thingzi-logic-twinkly) - Twinkly lights integration for node red
* Python class to interact with generation I device and IDA Pro loader of firmware binary in [Twinkly Twinkly Little Star by F-Secure LABS](https://labs.f-secure.com/blog/twinkly-twinkly-little-star/).

[![Gitter](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/xled-community/chat?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)