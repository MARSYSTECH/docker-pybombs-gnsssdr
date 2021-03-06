# GNSS-SDR Dockerfile

This repository contains a Dockerfile that creates a [Docker](https://www.docker.com/) image with [GNSS-SDR](http://gnss-sdr.org) and its dependencies installed via [PyBOMBS](https://github.com/gnuradio/pybombs). This includes [GNU Radio](http://gnuradio.org/) and drivers for a wide range of RF front-ends through [UHD](https://github.com/EttusResearch/uhd) and [gr-osmosdr](http://sdr.osmocom.org/trac/wiki/GrOsmoSDR).

This image uses [baseimage-docker](https://github.com/phusion/baseimage-docker), a special Docker image that is configured for correct use within Docker containers. It is Ubuntu, plus:

  * Modifications for Docker-friendliness.
  * Administration tools that are especially useful in the context of Docker.
  * Mechanisms for easily running multiple processes, without violating the Docker philosophy.
  * It only consumes 6 MB of RAM.

If you still have not done so, [install Docker](https://docs.docker.com/engine/getstarted/step_one/) and [verify your installation](https://docs.docker.com/engine/getstarted/step_three/).

Pull docker image
-----------

You can download (pull) the image via following command:

     $ docker pull carlesfernandez/docker-pybombs-gnsssdr



Build docker image
-----------

Go to the repository directory and run the following command:

     $ docker build -t carlesfernandez/docker-pybombs-gnsssdr .


Run docker image
-----------
Run:

    $ docker run --rm -t -i carlesfernandez/docker-pybombs-gnsssdr /sbin/my_init -- bash -l

Run with graphical environment:

This should work on most Linux X server machines and makes GNU Radio Companion accessible.

     $ docker run --rm -ti -e DISPLAY -v $HOME/.Xauthority:/root/.Xauthority \
     --net=host carlesfernandez/docker-pybombs-gnsssdr
