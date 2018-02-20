# caesar-container
Singularity container for CAESAR software tool

## **About**  
This repository provides the following Singularity recipe files:

* caesar-base: to build a Singularity base container for CAESAR tool (maintained at https://github.com/SKA-INAF/caesar.git). The built container will provide all the dependencies needed to build CAESAR:

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

* caesar: to build Caesar singularity from latest release using a local caesar base image.

## **How to build containers?**
WRITE ME
