# karma-virtualbox-ie11-launcher

**A Karma launcher for Internet Explorer 11 on VirtualBox.**

[![tests](https://img.shields.io/travis/chrisguttandin/karma-virtualbox-ie11-launcher/master.svg?style=flat-square)](https://travis-ci.org/chrisguttandin/karma-virtualbox-ie11-launcher)
[![dependencies](https://img.shields.io/david/chrisguttandin/karma-virtualbox-ie11-launcher.svg?style=flat-square)](https://www.npmjs.com/package/karma-virtualbox-ie11-launcher)
[![version](https://img.shields.io/npm/v/karma-virtualbox-ie11-launcher.svg?style=flat-square)](https://www.npmjs.com/package/karma-virtualbox-ie11-launcher)

The `karma-virtualbox-ie11-launcher` can be used to run karma tests on Microsoft Internet Explorer
11. It requires one the
[official virtual machines](https://developer.microsoft.com/en-us/microsoft-edge/tools/vms/)
provided by Microsoft which runs on VirtualBox.

## Installation

You can install the `karma-virtualbox-ie11-launcher` via npm:

```shell
npm install karma-virtualbox-ie11-launcher --save-dev
```

## Usage

To run tests on Microsoft Internet Explorer 11 Karma can be configured like that:

```js
// ...
browsers: [
    'VirtualBoxIE11'
],
// ...
customLaunchers: {
    VirtualBoxIE11: {
        base: 'VirtualBoxIE',
        keepAlive: true,
        snapshot: 'pristine',
        uuid: '66975e0d-14f7-4d79-7b8b-b3f6496f0a14'
    }
}
// ...
```

If you explicitly specify the plugins in your config file as well, make sure to add
`karma-virtualbox-ie11-launcher` to the list of plugins.

```js
// ...
plugins: [
    // ...
    'karma-virtualbox-ie11-launcher'
]
// ...
```

You may also want to increase the `captureTimeout` of Karma, if your VM takes very long to boot.

## Options

### keepAlive

If `true` the virtual machine will not be shut down after the tests.

### snapshot

An optional snapshot to which the virtual machine gets reset before starting it.

### uuid

The uuid of the virtual machine.
