# Score - Tlake-nodejs-service

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/htc-kubecon-na-2024/tlake-nodejs-service)

The workload is a simple containerized NodeJS app talking to a MySQL database.

[Score](https://score.dev/) is used to deploy the workload locally with `score-compose` in Docker, with `score-k8s` in Kubernetes or with `humctl` in Humanitec. See [Makefile](Makefile) for more details.

## Deploying

Locally:
```bash
make compose-up

make compose-test
```

In Kubernetes (`Kind`):
```bash
make kind-create-cluster

make kind-load-image

make k8s-up

make k8s-test
```

In Humanitec:
```bash
humctl login

humctl config set org FIXME
humctl config set app tlake-nodejs-service
humctl config set app development

make htc-up
```