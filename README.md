# meteor-example-on-openshift
Deploy a meter sample app to openshift

## Optional
Build sample image using https://dockerize.io/guides/docker-meteor-guide
This repo will be using this image quay.io/gbengataylor/meteor-tutorial:1.0

## Deploy

### Create Service Account
```sh
oc create serviceaccount useroot
oc adm policy add-scc-to-user anyuid -z useroot
```

### Deploy App

### Test App
