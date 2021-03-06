# Yeetlight

Yeetlight is a lightweight Yeelight smartlights web control panel.

It was created as a way so that I wouldn't *yeet* my *lights* when
interacting with their official smartphone app.

## Features

Remote control of the Yeelight/Xiaomi smartlights including:
- power on/off
- brightness
- color temperature

Additional features:
- simple UI
- support for multiple smartlights in a single panel
- responsive web design

![](https://raw.githubusercontent.com/vifon/yeetlight/master/example/screenshot1.png)

## Dependencies

A [Go](https://golang.org/) compiler is needed to build
the application.

## Usage

Build and run with:

    $ go build
    $ ./yeetlight -iface 0.0.0.0:8080

The `-iface …` argument may be omitted if the above example is the
intended value, i.e. exposing the control panel on all network
interfaces on `8080` TCP port.

Afterwards edit `public/config.json` according to the intended
smartlight setup.  The `bulbs` config option should contain a mapping
in one of these forms:

    "Bulb name": {
      "addr": "192.168.xxx.xxx"
    }

…or if no name is needed…

    "192.168.xxx.xxx": {}

Open `http://localhost:8080` in a web browser.

## Security considerations

*Yeetlight* was written with the assumption it's being run inside
a fully trusted network on a device like Raspberry Pi, so no
authentication is used at all.

## Roadmap

- [X] implement the Yeelight API communication in Go and eliminate the
      `yeecli` dependency
- [ ] add support for device groups
