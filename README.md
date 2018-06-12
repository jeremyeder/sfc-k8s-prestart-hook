# oci-decorator
Prestart Hook providing additional functionality to containers

Copy the oci-onload.cfg configuration file into place.  This file dictates the files and devices that the hook will make available in each container.

```
yum install cmake yajl-devel libconfig-devel
mkdir -p /etc/oci-decorator/oci-decorator.d
cp oci-onload.cfg /etc/oci-decorator/oci-decorator.d/
```

Build and install the binary
```
cmake
make
make install
```

The installation step will place the binary into the hook directory at ```/usr/libexec/oci/hooks.d/oci-decorator```.

Notes:
1) Prestart hooks require a container runtime that supports them.  Examples of this are CRI-O or Red Hat's distribution of docker.
2) Red Hat Enterprise Linux 7 is currently required to build the hook due to the versions of libraries used.  This is a TODO item to fix.
