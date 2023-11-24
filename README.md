# Docker Aseprite container

Modified repository by [nilsve](https://github.com/nilsve/docker-aseprite-linux).

This repository allows you to compile Aseprite without installing any build tools. All that is required is Docker.

## Usage

Docker must be installed on your system. You can find instructions on how to install Docker for your system [here](https://docs.docker.com/get-docker/).

1. Clone this repository

```bash
git clone https://github.com/pixellab-code/docker-aseprite-linux.git
```

2. Build aseprite

```bash
make build
```

3. Grab a cup of coffee, since this can take quite a while (compiling build dependencies, skia, and aseprite)

4. You can now find the compiled version of Aseprite in the `output/aseprite/build/bin` folder

## FAQ

If you get the following error when running Aseprite: `./aseprite: error while loading shared libraries: libdeflate.so.0: cannot open shared object file: No such file or directory`, make sure you have libdeflate installed on your system.

```bash
sudo apt install -y libdeflate0 libdeflate-dev
```

If you get the following error: `./aseprite: error while loading shared libraries: libcrypto.so.1.1: cannot open shared object file: No such file or directory`, you'll want to install the OpenSSL 1.1 package/library. You may have only OpenSSL 3.x installed, meanwhile Aseprite still uses the v1.1 library.

- On Ubuntu try:

```
sudo apt install -y libssl1.1
```

- On Arch / Arch based distros, run

```bash
sudo pacman -Syu openssl-1.1
```
