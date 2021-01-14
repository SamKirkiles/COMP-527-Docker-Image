# COMP 527 Docker Image

Creates a docker container with SML and Tutch 0.53 pre installed.

## Using Tutch with vim/emacs

Prerequisites: make sure docker is installed on your machine (any OS)

1. Clone the repo aanywhere 
2. cd into `.devconainer` and run `docker build .`
3. Run `docker image ls` and copy the name of the recently created image (it should look something like `49824fdefcee`)
4. Run `docker run -it <name>` to open a shell in yout docker container. 
CD into `.devcontainer` and run `docker build .` to get started. Then run `docker image ls` anad copy the name of the continer. Finally run `docker run -it <name>` to start the instance
