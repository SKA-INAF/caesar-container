# caesar-container
Singularity container for CAESAR software tool

## **About**  
This repository provides the following Singularity recipe files:

* **caesar-base**: recipe to build a Singularity base container for CAESAR tool (maintained at https://github.com/SKA-INAF/caesar.git) from a docker Ubuntu image (Ubuntu 16 xenial). The built container will provide all the dependencies needed to build CAESAR:

   - ROOT
   - OpenCV
   - BOOST
   - Log4Cxx
   - Jsoncpp
   - cfitsio
   - protobuf
   - MPICH
   - OpenMPI
   - python 2.7 + modules (numpy, astropy, pyfits)
	
The container is used mainly to build CAESAR upon it.

* **caesar**: recipe to build a CAESAR singularity container from latest release (https://github.com/SKA-INAF/caesar.git)) using a local caesar base image (built using previous recipe).

## **How to build CAESAR images?**

### **Prerequisites**
To build images on your system you must have a recent version of Singularity (https://github.com/singularityware/singularity.git) installed. CAESAR makes use of singularity apps so a singularity version >2.3 is required. A system-wide installation is required, e.g. you need root permissions on the build system.   

### **Build images**
To build images do the following:

```singularity build [IMAGE_NAME] [RECIPE_FILE]```

where:

* ```IMAGE_NAME```: Name of image file you want to be created (e.g. caesar-base.simg for base container or caesar.simg for caesar container).   
* ```RECIPE_FILE```: Name of the recipe file provided in this repository (e.g. Singularity.xenial)

## **How to use CAESAR images?**
To see the list of apps installed in your CAESAR container (say named ```caesar.simg```):

* ``` [...]$ singularity apps caesar.simg```

To run one app (say the ```sfinder``` app):

* ```[...]$ singularity run --app sfinder caesar.simg --config=myconfig.cfg```
```

