build:
	docker-buildx build \
		--platform linux/amd64,linux/arm64/v8 \
		--tag ghcr.io/fedemengo/googletest:1.13.0 \
		--label "org.opencontainers.image.source=https://github.com/fedemengo/docker-images" \
		--label "org.opencontainers.image.licenses=MIT" \
		--push .
