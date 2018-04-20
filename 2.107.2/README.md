# Content Description

- Dockerfile
  - uses the full 2.107.2 jenkins/jenkins image as base and has docker version 18.03.0-ce insatlled
- Dockerfile_slim
  - uses the slim 2.107.2 jenkins/jenkins image as base and too has docker version 18.03.0-ce insatlled
- Dockerfile_alpine
  - uses the alpine 2.107.2 jenkins/jenkins image as base and has the docker version 17.12.1-ce insatlled
  since its based on alpine 3.7 wich is not compatible with 18.03.0 (see README.md in root of this repo)
