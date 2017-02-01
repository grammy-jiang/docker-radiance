# docker-radiance
Latest version of Radiance compiled in Docker.

Current the latest version of Radiance is 5.0.

Because of the interactive of `makeall` script, and I don't want to crack it, Dockerfile only install all dependenices, then login to the container to compile, make commit the change into the final image.

## Usage
1. Run docker build in folder `docker-radiance`:
```shell
docker build . -t radiance:5.0
```

2. Run it and login to the contain:
```shell
docker run -it radiance:5.0
```

3. Compile:
```shell
cd ~/downloads/ray/
./makeall install clean
```

## Notice
1. Let debian choose the fastest mirror to update and install packages, by using `http://httpredir.debian.org/debian` in `/etc/apt/sources.list`.

## Related Links:
- [Radiance WWW Server](http://radsite.lbl.gov/radiance/HOME.html)
- [NREL/Radiance: Mirror of the master Radiance cvs source repo, used for the creation of Radiance installers for the NREL OpenStudio project](https://github.com/NREL/Radiance)
- [Debian worldwide mirror sites](https://www.debian.org/mirror/list)
