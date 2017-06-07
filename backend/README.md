### Installation

Build your Dockerfile. 
```sh
# It shall download `flite` binary into alpine. We will run it via 'docer exec'.
$ docker build -t roy/say .
```

### Usage
To view available options:
```sh
$ docker run --rm roy/say flite -h 

# it shall produce output.wav that says "hello", in docker container.
$ docker run --rm roy/say flite -t hello -o output.wav
```

Next, to export output from docker container, map the volumes
```sh
# -w : set as working directory
docker run --rm -v $(pwd)/data:/data -w /data roy/say flite -t hello -o output.wav
```

Finally, to play
```
$ afplay data/output.wav
```

### With main.go

`main.go` runs flite binary that produces `output.wav` of first argument.


With app (main.go's executable) in container, you may now run:
```sh 
docker run --rm -v $(pwd)/data:/data -w /data roy/say "hello there"
```