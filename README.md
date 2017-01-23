# asnelling/node-winbuildtools

Docker image with Node.js and build tools (VC++, Python 2.7) on Windows Server Core.

## Software
- Base Image: Windows Server Core
([microsoft/windowsservercore](
  https://hub.docker.com/r/microsoft/windowsservercore/))
- Node.js - your choice of versions:
    - v7.4.0 (asnelling/node-winbuildtools:7.4.0)
    - v6.9.4 (asnelling/node-winbuildtools:6.9.4)
- [Python 2.7.13](https://www.python.org/downloads/release/python-2713/)
- [Microsoft Visual C++ Build Tools 2015](http://landinghub.visualstudio.com/visual-cpp-build-tools)

These satisfy the dependencies needed to build native modules with [node-gyp](https://github.com/nodejs/node-gyp)

## Usage

### To use this Docker Image
Create a [Dockerfile](https://docs.docker.com/engine/reference/builder) in the root of your project directory, and place this at the top:
```Dockerfile
FROM asnelling/node-winbuildtools

# or specify a tag (node verion)
# e.g.: FROM asnelling/node-winbuildtools:6.9.4
FROM asnelling/node-winbuildtools:<tag>
```

### Available Tags
You may optionally specify a Node.js version in the tag (e.g.: `asnelling/node-winbuildtools:7.4.0`) when using this image. The node versions below are available:
- 6.9.4 (`asnelling/node-winbuildtools:6.9.4`)
- 7.4.0 (`asnelling/node-winbuildtools:7.4.0`)
