# example-container-image-supply-chain-security

Example repository that demonstrates a supply chain security workflow using Syft, Grype, Cosign using Cloudsmith as the Container Registry

o run this example yourself:

1. I have built a docker image with cosign, syft and grype from the Dockerfile, https://github.com/ciaracarey/example-container-image-supply-chain-security/blob/main/.github/workflows/Dockerfile and have it hosted on Cloudsmith. It's a public repo and you can fetch it using: 
``` 
docker pull docker.cloudsmith.io/cloudsmith/examples/example-ci:latest
```
Otherwise you can build it from https://github.com/ciaracarey/example-container-image-supply-chain-security/blob/main/.github/workflows/Dockerfile

2. In the 2 yaml workflows build-and-publish.yaml and nightly.yaml, you will need to fork https://github.com/ciaracarey/example-container-image-supply-chain-security and add your add the private key and password as secrets for authentication into your Docker registry.

3. In your forked repo, the 2 yaml workflows build-and-publish.yaml and nightly.yaml, you will need to update the location of the docker image from step 1 if you have changed it and use your username instead of mine.

