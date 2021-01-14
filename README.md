# COMP 527 Docker Image

Creates a docker container with SML and Tutch 0.53 pre installed.

## Using Tutch with vim/emacs

Prerequisites: make sure docker is installed on your machine (any OS)

1. Clone the repo anywhere 
2. cd into `.devconainer` and run `docker build -t tutch .`
3. Run `docker run -it --rm --name tutch -v <FULL PATH TO MOUNT TO IMAGE>:/root/ tutch` to open a shell in your docker container. Important: relative paths will not work. 
4. Start using tutch with `tutch`

### Example
For example, I would like to mount my tuch_files folder located at `/Users/samkirkiles/Documents/COMP-527-Docker-Image/tutch_files`

So I would run `docker run -it --rm --name tutch -v /Users/samkirkiles/Documents/COMP-527-Docker-Image/tutch_files:/root/ tutch`
