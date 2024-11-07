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

#### Example

```bash
$ nimdocgen websitegenerator
Generating docs...
  Verifying dependencies for websitegenerator@2.1.0
 Generating documentation for websitegenerator (from package websitegenerator) using doc backend
...
Finished doc generation!
Moving docs to '/home/niro/Git/nirokay.github.io/nim-docs/'...
Add, commit and push changes of directory '/home/niro/Git/nirokay.github.io/nim-docs/websitegenerator' with git? [Y/n] y
[main 7981721] Updated docs for 'websitegenerator'
 14 files changed, 14 insertions(+), 14 deletions(-)
...
remote: Resolving deltas: 100% (17/17), completed with 17 local objects.
To github.com:nirokay/nirokay.github.io
   f752fad..7981721  main -> main
/home/niro/Git/websitegenerator
Everything went well! :)
```

### python-webserver

Bash script to quickly start a python3 webserver.

#### Example

```bash
$ python-webserver 80 -d .
[sudo] password for root: ******
Serving HTTP on 0.0.0.0 port 80 (http://0.0.0.0:80/) ...
```

### replace

Lua script that forwards `$1` and `$2` to `sed "s/$1/$2/g"` (I always forget the `sed` syntax, so
this is the reason this exists...)

#### Example

```bash
$ echo "this is an entry:more data:hello world" | replace " " "_" | replace ":" "\t"
this_is_an_entry        more_data       hello_world
```

### updateall

Bash script that updates all software supporting multiple package managers, determining which
ones are installed at runtime.

> * `-a`,`--async` Performs updates in parallel by opening multiple terminal emulator windows (not all of them may be supported)

#### Example

```bash
$ updateall
The following commands will be executed:
        sudo zypper up
        sudo flatpak update -y
        gitman pull

Continue? [Y/n] y
Continuing...

Executing 'sudo zypper up'
[sudo] password for root: ******
...
```

### wtf-is-this

Utility to get information about all the scripts or a single one in this project.

See [the script](scripts/updateall) for up-to-date documentation on the scripts!

#### Examples

```bash
$ wtf-is-this
gac              --> Bash script to bulk-commit all changes.
nimdocgen        --> Bash script to automatically generate and deploy docs for projects using the Nim programming language.
python-webserver --> Bash script to quickly start a python3 webserver.
replace          --> Lua Script that simplifies the 'sed' syntax for easy character replacement.
updateall        --> Bash script to update all packages, supports many package managers.
    -a,--async       Perform updates in parallel (opens multiple terminal windows, not all are supported)
wtf-is-this      --> Bash script to inform you about what script does what... THIS is it actually!!
zipdir           --> Bash script to zip a whole directory. It has the same name with only '.zip' appended.
```

```bash
$ wtf-is-this updateall
updateall        --> Bash script to update all packages, supports many package managers.
    -a,--async       Perform updates in parallel (opens multiple terminal windows, not all are supported)
```

### zipdir

Zips an entire directory and puts the zip file next to it with the same name with a `.zip`
appended.

#### Example

```bash
$ tree
.
└── some-files
    ├── important-document.txt
    └── not-sus-file.txt

2 directories, 2 files

$ zipdir some-files
  adding: some-files/ (stored 0%)
  adding: some-files/important-document.txt (stored 0%)
  adding: some-files/not-sus-file.txt (deflated 5%)

$ tree
.
├── some-files
│   ├── important-document.txt
│   └── not-sus-file.txt
└── some-files.zip

2 directories, 3 files
```

## Contributions

Contributions are always welcome. For example by expanding the supported package managers in
[`scripts/updateall`](scripts/updateall).

## Licence

These scripts are distributed under the `GPL-3.0` licence.
