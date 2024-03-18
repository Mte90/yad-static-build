# Yad Static build for Linux

This repository is just a CI that publish a GH release with the latest [yad](https://github.com/v1cont/yad) version compiled in a static binary with everything, so it is self-contained.

*Right now doesn't compile with gtk-spell support to keep lightweight.*

## How works

[CI](https://github.com/Mte90/yad-static-build/blob/main/.github/workflows/build.yaml)

* Check if a tag 'v\*' or 'nighly-\*' exists
* Initialize a ubuntu docker image
* Install dev dependencies
* Download the latest version from the yad repository
* Compile it using the `--enable-standalone` official parameter
* Using [packelf](https://github.com/oufm/packelf) generate a static binary with everything
* Zip it and update the release with the asset

The advantage of this, is that if you try the same workflow in your machine the build can be 80~mb (in my case) as find more library that the package could need.
Instead in this way it is just the stuff that need to work.

# Download

Go on [https://github.com/Mte90/yad-static-build/releases](https://github.com/Mte90/yad-static-build/releases).

# Tested

* Debian Sid

![image](https://github.com/Mte90/yad-static-build/assets/403283/b6535214-e074-4aaa-9b70-f92af3dc1919)

* SteamOS (2022 build)

![image](https://github.com/Mte90/yad-static-build/assets/403283/150cbf8b-eb47-4b49-a241-beefd5649486)
