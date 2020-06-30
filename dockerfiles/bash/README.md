# Usage
With this Dockerfile, you can copy anything (even pre-compiled binaries) on `install` directory.

The entry point is `install/run.sh`. 

# How to compile and run
```bash
$ docker run -v "$(pwd):/work" -w /work gcc bash build.sh
$ docker build -t icfp-contest-2020-bash .
Sending build context to Docker daemon  24.58kB
Step 1/4 : FROM debian:buster-20200607-slim
 ---> 43e3995ee54a
Step 2/4 : WORKDIR /source
 ---> Using cache
 ---> b01b19cb2a94
Step 3/4 : COPY install .
 ---> Using cache
 ---> 2b2ff2986329
Step 4/4 : ENTRYPOINT ["bash", "./run.sh"]
 ---> Using cache
 ---> 9db3deb685bb
Successfully built 9db3deb685bb
Successfully tagged icfp-contest-2020-bash:latest
$ docker run icfp-contest-2020-bash
Hello World!
Hello World from pre-compiled binary!
```
