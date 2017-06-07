
# cross compile main.go to app artifact, add to container and remove artifact.
build:
	GOOS=linux go build -o app
	docker build -t roy/say .
	rm -f app