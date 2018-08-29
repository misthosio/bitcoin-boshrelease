# BOSH release for bitcoin

This BOSH release and deployment manifest deploy a cluster of bitcoin.

## Usage

This repository includes base manifests and operator files. They can be used for initial deployments and subsequently used for updating your deployments:

```plain
export BOSH_ENVIRONMENT=<bosh-alias>
export BOSH_DEPLOYMENT=bitcoin
git clone https://github.com/cloudfoundry-community/bitcoin-boshrelease.git
bosh deploy bitcoin-boshrelease/manifests/bitcoin.yml
```

If your BOSH does not have Credhub/Config Server, then remember `--vars-store` to allow generation of passwords and certificates.

### Update

When new versions of `bitcoin-boshrelease` are released the `manifests/bitcoin.yml` file will be updated. This means you can easily `git pull` and `bosh deploy` to upgrade.

```plain
export BOSH_ENVIRONMENT=<bosh-alias>
export BOSH_DEPLOYMENT=bitcoin
cd bitcoin-boshrelease
git pull
cd -
bosh deploy bitcoin-boshrelease/manifests/bitcoin.yml
```
