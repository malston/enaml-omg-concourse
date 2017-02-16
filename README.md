# enaml-omg-concourse

```bash
  $ cd ~/workspace/enaml-omg-concourse
  ## login to bosh (e.g. bosh --ca-cert ~/workspace/concourse-pipelines-config/credentials/bosh_ca_cert target 10.0.0.31)
  $ bosh cloud-config > cloud-config.yml
  $ bosh update cloud-config cloud-config.yml
  $ ./deploy-concourse
  $ bosh download manifest concourse concourse.yml
  ## modify concourse.yml manifest for your needs
  $ bosh deployment concourse.yml
  $ bosh -n deploy
```