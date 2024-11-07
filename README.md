# Shell-Utils

## About

This is a collection of shell utility programs for your and my convenience!

## Installation

You can clone this repository and simply add the `scripts` subdirectory to your path!

## Scripts

### gac

Bash script to bulk-commit all changes. Basically an alias to `git add . && git commit -m $*`

### nimdocgen

Bash script to automatically generate and deploy docs for projects using the Nim programming
language.

### python-webserver

Bash script to quickly start a python3 webserver.

### replace

Lua script that forwards `$1` and `$2` to `sed "s/$1/$2/g"` (I always forget the `sed` syntax, so
this is the reason this exists...)

```bash
$ echo "this is an entry:more data:hello world" | replace " " "_" | replace ":" "\t"
this_is_an_entry        more_data       hello_world
```

### updateall

Bash script that updates all software supporting multiple package managers, determining which
ones are installed at runtime.

> * `-a`,`--async` Performs updates in parallel by opening multiple terminal emulator windows (not all of them may be supported)

### wtf-is-this

Utility to get information about all the scripts or a single one in this project.

See [the script](scripts/updateall) for up-to-date documentation on the scripts!

### zipdir

Zips an entire directory and puts the zip file next to it with the same name with a `.zip`
appended.

## Contributions

Contributions are always welcome. For example by expanding the supported package managers in
[`scripts/updateall`](scripts/updateall).

## Licence

These scripts are distributed under the `GPL-3.0` licence.
