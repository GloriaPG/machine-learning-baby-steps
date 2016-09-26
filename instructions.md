```{r, engine='bash', count_lines}
$ docker build --rm --force-rm -t gloriapg/r-glou .
```

```{r, engine='bash', count_lines}
# we need X11 for the graph to display, alternatively
# you can save to a file that is in a bind-mounted dir
# or you can docker cp the file to the host :)

$ docker run -it --name analytics \
    -v /tmp/.X11-unix:/tmp/.X11-unix \
    -e DISPLAY=unix$DISPLAY \
    gloriapg/r-glou

```

```{r, engine='bash', count_lines}
# bind mount your data
$ docker run -v $(pwd)/data:/home/user/data \
    -it --name testing \
    -v /tmp/.X11-unix:/tmp/.X11-unix \
    -e DISPLAY=unix$DISPLAY \
    gloriapg/r-glou
```