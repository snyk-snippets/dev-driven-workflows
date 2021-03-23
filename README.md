# Tutorial repo to accompany Snyk Blogs
[![Known Vulnerabilities](https://snyk.io/test/github/snyk/goof/badge.svg?style=flat-square)](https://snyk.io/test/github/snyk/dev-driven-workflows)

This repository is meant as a simple tutorial aid to accompany the Snyk [Developer Drivien Worklows](https://snyk.io/blog) blog article.  It is a stripped down copy of https://github.com/snyk/goof.

**_TODO: Update above with actual blog URL when published_**


## Dockerfile related
There are 3 Dockerfile examples, each of which can be coppied over the `Dockerfile` as you step through the article:

1. `Dockerfile-initial` - Unoptimized and broken file
1. `Dockerfile-hadolint-fixes` - Edits applied per hadolint and fixes `docker build` error
1. `Dockerfile-nonroot` - Builds on the above with fix to stop running as root by default

Also, `pre-commit-hook.sample` can be copied into your repo clone's `.git/hooks/pre-commit` to enforce linting at commit (see blog for detais)

## Kubernetes related
In the `/manifests` directory, you will find 3 versions of the `goof-deployment.yaml` file.  As above, copy any of the following versions over it as you work through the article:

1. `goof-deployment.yaml-initial` - Basic deployment of the `goof` application (build via the Dockerfile above) as well as a stock `mongodb` container.
1. `goof-deployment.yaml-nonroot` - Add runtime enforcement to stop `goof` from running as the root user
1. `goof-deployment.yaml-nonroot-drop-capabilities` - Builds on the above with unnessesary Linux capabilities dropped for the `goof` container

There is also a `goof-services.yaml` file allong side these that needs to be deployed to expose the app and db on the network.

### For kind Users
`kind-config.yaml` is provided for those running [Kubernetes in Docker (kind)](https://kind.sigs.k8s.io), an example cluster configuration file is provided to enable localhost access to the service endpoint.