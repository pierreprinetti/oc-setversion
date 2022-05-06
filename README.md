# oc-setversion

Sets the desired version of `oc` and `openshift-install` for this particular `$PWD` and its subdirectories.
Downloads and installs the binaries if they are not available already.

## Install

```shell
curl -sSL \
	--url 'https://raw.githubusercontent.com/pierreprinetti/oc-setversion/main/oc-setversion' \
	> ~/.local/bin/oc \
	&& chmod +x ~/.local/bin/oc
```

You can replace `/.local/bin/oc` with any directory in `$PATH`.

## Update

Same as Install.

## Use

```shell
$ oc setversion 4.7.1
# Client Version: 4.7.1
# [...]
oc get pods
```

Use `latest-4.11` to automatically select the latest 4.11 nightly.

### Reset this directory's setting

```shell
oc setversion
```

## Reset to factory settings

```shell
rm "${XDG_CONFIG_HOME:-${HOME}/.config}/oc-setversion/paths.conf"
```

## What is my config again?

```shell
cat "${XDG_CONFIG_HOME:-${HOME}/.config}/oc-setversion/paths.conf"
```

## Warning

This script locally installs `oc` and `openshift-install` for every requested
version in `${HOME}/.local/bin`. The size of that folder can grow quickly!
