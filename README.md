# node-touch

For all your node touching needs.

This is a fork of Isaac Schlueter's [`touch`](https://github.com/isaacs/node-touch) module. This adds the ability to use touch from npm scripts in a cross platform manner, like so:

```json
{
  "scripts": {
    "touch": "touch foo",
    "remove": "rimraf foo"
  }
}
```

## Installing

```bash
npm install --save-dev https://github.com/shovon/node-touch/tarball/v0.1.0
```

## CLI Usage:

See `man touch`

## API Usage:

```javascript
var touch = require("touch")
```

Gives you the following functions:

* `touch(filename, options, cb)`
* `touch.sync(filename, options)`
* `touch.ftouch(fd, options, cb)`
* `touch.ftouchSync(fd, options)`

## Options

* `force` like `touch -f` Boolean
* `time` like `touch -t <date>` Can be a Date object, or any parseable
  Date string, or epoch ms number.
* `atime` like `touch -a` Can be either a Boolean, or a Date.
* `mtime` like `touch -m` Can be either a Boolean, or a Date.
* `ref` like `touch -r <file>` Must be path to a file.
* `nocreate` like `touch -c` Boolean

If neither `atime` nor `mtime` are set, then both values are set.  If
one of them is set, then the other is not.
