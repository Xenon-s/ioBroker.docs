![Logo](admin/zwave2.svg)

# ioBroker.zwave2

[![node](https://img.shields.io/node/v/iobroker.zwave2.svg)
![npm](https://img.shields.io/npm/v/iobroker.zwave2.svg)](https://www.npmjs.com/package/iobroker.zwave2)
[![changelog](https://img.shields.io/badge/read-Changelog-informational)](CHANGELOG.md)

![Number of Installations](http://iobroker.live/badges/zwave2-installed.svg)
![Number of Installations](http://iobroker.live/badges/zwave2-stable.svg)

![Test and Release](https://github.com/AlCalzone/iobroker.zwave2/workflows/Test%20and%20Release/badge.svg)
[![Language grade: JavaScript](https://img.shields.io/lgtm/grade/javascript/g/AlCalzone/ioBroker.zwave2.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/AlCalzone/ioBroker.zwave2/context:javascript)
[![Translation status](https://weblate.iobroker.net/widgets/adapters/-/zwave2/svg-badge.svg)](https://weblate.iobroker.net/engage/adapters/?utm_source=widget)

<h2 align="center">Z-Wave for ioBroker. But better.</h3>

Z-Wave 2 is a brand new Z-Wave implementation for ioBroker. It is based on [`zwave-js`](https://github.com/AlCalzone/node-zwave-js), which was written from the ground up for your benefit.

Unless [`ioBroker.zwave`](https://github.com/ioBroker/ioBroker.zwave/) it does not require `OpenZWave`. This means that the installation and updates are fast, and no compilation of static libraries and other complicated steps are necessary.

Furthermore, some devices just don't work in the original adapter, e.g. the Fibaro Roller Shutter 3.

Easy usage in ioBroker was kept in mind during the whole development. For example, some devices reuse configuration parameters to configure many different things. In this adapter, most of them are split into separate states and no complicated math is necessary:
| Config params in ioBroker.zwave2 | vs | Config params in ioBroker.zwave |
| --- | --- | --- |
| ![](docs/de/images/config-params.png) | vs | ![](docs/de/images/config-params-legacy.png) |

---

## Documentation and usage
* [FAQ](docs/en/FAQ.md)
* [Troubleshooting](docs/en/troubleshooting.md) · [bei Problemen](docs/de/bei-problemen.md)

---

## Changelog
[Older changes](CHANGELOG_OLD.md)
<!--
	Placeholder for next versions:
	### __WORK IN PROGRESS__
-->
### 1.10.0 (2021-04-29)
* The associations tab now shows the name of devices along with their node ID
* Associations can now also be managed on the endpoints of a node
* Experimental support for updating the embedded configuration files from the adapter configuration
* Support firmware updates with `*.hec` files
* Reduced traffic after controlling devices that report automatically
* Fixed an issue where `Basic CC` values were not stored correctly
* Added and updated many device configuration files
* Stability improvements
* Dependency updates

### 1.9.3 (2021-04-10)
* Restored the old behavior for devices that report their values via the root endpoint
* Some minor config file changes

### 1.9.2 (2021-04-05)
Upgraded to `zwave-js` version `7.1.0`. Notable changes include:
* Added reporting of usage statistics. For details, refer to the `node-zwave-js` documentation.
* Better support for 700-series Z-Wave sticks
* Notification values are no longer auto-reset to idle after 5 minutes by default. This behavior can now be enabled per device if necessary.
* Several stability improvements

For a full list of changes, check out https://github.com/zwave-js/node-zwave-js/blob/master/CHANGELOG.md

### 1.9.0 (2021-03-16)
* Upgraded to `zwave-js` version 7
* Nodes with a completed interview are no longer queried for all their values when restarting. As a result the adapter is now ready much much faster after a restart, but you'll see many yellow values until the devices have sent updated data.
* The device list in the configuration dialog now displays a better type for the devices, for example `Wall Controller` instead of `Routing Slave`
* Network heal no longer times out early in large networks
* Fixed a crash: `supportedCCs is not iterable`. If this happens to you, re-interview affected devices.
* Relaxed the checks when a report gets mapped from the root endpoint to higher endpoints
* Some encrypted messages that were previously dropped are now accepted
* Prevent the interview of sleeping nodes to get stuck until a re-interview under certain circumstances
* After a restart, sleeping nodes have their status correctly determined even if they weren't interviewed completely before
* Notification variables are now auto-idled after 5 minutes as it was intended, not after 5 hours
* The `deltaTime` and `previousValue` values for the Meter CC are now hidden
* Fixed a crash that could happen after node inclusion
* Tons of new and improved device configuration files

### 1.8.12 (2021-02-23)
* Implemented `Scene Actuator Configuration CC` and `Scene Controller Configuration CC`
* Fixed an issue where sleeping nodes could block the send queue when it is not yet known whether they support `Wake Up CC`
* Fixed a crash that could happen while logging a message while the driver is not ready yet
* Fixed a crash that could happen while trying to bootstrap a device that does not respond after inclusion
* The state value in `Thermostat Fan Mode CC` is now readonly
* Configuration parameters may now have a unit
* Tons of new and improved device configuration files
* Unsolicited reports are no longer incorrectly mapped to all endpoints

## License

MIT License

Copyright (c) 2019-2021 AlCalzone

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
