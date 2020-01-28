Once you have docker installed, and you can do something like:

```
docker run hello-world
```

Copy the FORTRAN files for REFPROP into folder `RP10src` in this folder

In this folder, build the image

```
docker build -t rpub18 .
```

Bash into the container

```
docker run -it -v"$(PWD)":/shared  -t rpub18 bash
```

Then inside the container:

```
cd /REFPROP-cmake/build
cmake .. -DREFPROP_FORTRAN_PATH=/shared/RP10src
cmake --build .
```
