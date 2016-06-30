# Bosh release for ClamAV

If you need the [ClamAV](https://www.clamav.net/) anti-virus product in your infrastructure then deploy this BOSH release.

## Usage

### Create & Upload the BOSH release

To use this BOSH release, first create the dev release, then the final release, then upload it to your BOSH director:

```
bosh target BOSH_HOST
git clone https://github.com/kartiklunkad26/clamav-boshrelease.git
cd clamav-boshrelease
bosh create release --force
bosh create release --force --final
bosh upload release
```
## Creating a Bosh Add-On for ClamAV

### Create a BOSH deployment manifest 

Please refer to the file example-manifest.yml for an example of the deployment manifest for a BOSH Add-on. 

### Update the runtime-config

Using the previous created deployment manifest, now we can deploy it:

```
bosh update runtime-config clamav-addon.yml
bosh -n deploy
```




