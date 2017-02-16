# enaml-omg-concourse

Use this repo to deploy [concourse](https://concourse.ci) using [omg](https://github.com/enaml-ops/omg-cli) -- a cli for [enaml](https://github.com/enaml-ops/enaml).
Enaml is a third-party [bosh](https://bosh.io/) deployment manifest generation tool. `omg` deploys a bosh release that's been pre-configured for you by enaml.

* Read [instructions](https://github.com/enaml-ops/omg-cli#bosh-deployed-concourse) to deploy concourse with omg or just run [deploy-concourse](./deploy-concourse) like below.

```bash
  $ cd ~/workspace/enaml-omg-concourse
  ## login to bosh (e.g. bosh --ca-cert ~/workspace/concourse-pipelines-config/credentials/bosh_ca_cert target 10.0.0.31)
  $ bosh cloud-config > cloud-config.yml
  ## reserve ips for concourse
  $ bosh update cloud-config cloud-config.yml
  $ ./deploy-concourse
  $ bosh download manifest concourse concourse.yml
  ## modify concourse.yml manifest for your needs
  $ bosh deployment concourse.yml
  $ bosh -n deploy
```