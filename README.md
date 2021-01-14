# COMP 527 Docker Image

Creates a docker container with SML and Tutch 0.53 pre installed.

## Using Tutch with vim/emacs

Prerequisites: make sure docker is installed on your machine (any OS)

1. Clone the repo anywhere 
2. cd into `.devconainer` and run `docker build -t tutch .`
3. Run `docker run -it tutch` to open a shell in your docker container. 
