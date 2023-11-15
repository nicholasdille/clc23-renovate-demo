# Ubuntu

Opinionated customizations of the [official image for Ubuntu](https://hub.docker.com/_/ubuntu)

- [Code](https://github.com/nicholasdille/images/tree/main/ubuntu/22.04)
- [Container image](https://hub.docker.com/r/nicholasdille/ubuntu)
- [Upstream container image](https://hub.docker.com/_/ubuntu)

## Quick reference

- Maintained by:

    [Nicholas Dille](https://github.com/nicholasdille)

- Where to get help:

    [GitHub issues](https://github.com/nicholasdille/images/issues)

## Supported tags and respective `Dockerfile` links

- [`22.04`, `bionic`](https://github.com/nicholasdille/images/blob/main/ubuntu-22.04/Dockerfile)

## Quick reference (cont.)

- Where to file issues:

    [GitHub issues](https://github.com/nicholasdille/images/issues)

- Supported architectures:

    amd64, arm64

## Security

The container image is rebuilt daily.

Renovate is used to propose an update whenever the upstream tag ubuntu:22.04 is changed (using digesst pinning). The pull request is automatically tested and merged.

The container image comes with build attestation and a Software Bill of Materials (SBoM):

- Show build attestation: `docker buildx imagetools inspect nicholasdille/ubuntu:22.04 --format '{{ json .Provenance }}'`
- Show SBoM: `docker buildx imagetools inspect nicholasdille/ubuntu:22.04 --format '{{ json .SBOM }}'`

## License

See [upstream container image](https://hub.docker.com/_/ubuntu)