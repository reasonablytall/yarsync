# yarsync
A quick, simple, and swashbuckling tool for synchronizing directories

## Install

Clone this repository and move `yarsync` somewhere in your path, or call it directly.

### Dependences

yarsync requires `rsync` as well as `inotifywait` from `inotify-tools`.

## Usage

Specify `src` and `dest` directories, and yarsync will keep `dest` synchronized with `src` until exited. `dest` can be a network directory over ssh, like below:

```sh
yarsync ship/ seven@sea.s:~/ &

touch ship/cannon.ball
# cannon.ball now exists in both ship/cannon.ball and seven@sea.s:~/ship/cannon.ball
# changes to  ship/cannon.ball will be mirrored in  seven@sea.s:~/ship/cannon.ball
```

## Options

See `yarsync -h` for a list of all options.

* `yarsync --delete src dest` will delete files in `dest` if they aren't in `src` to keep both sides ship-shape.

* `yarsync --exclude=swabbie src dest` will exclude the file/directory `swabbie` from synchronization.
`--exclude` can be specified multiple times.
