# meteor-example-on-openshift
Deploy a meter sample app to openshift (persistence not included)

## Optional
Build sample image using https://dockerize.io/guides/docker-meteor-guide.

This repo will be using this image quay.io/gbengataylor/meteor-tutorial:1.0 . To use your image that is hosted in a registry, edit meteor-deployment.yaml and replace the image name

## Deploy

### create project
```sh
oc new-project meteor-on-openshift
```

### Create Service Account
```sh
oc create serviceaccount useroot
oc adm policy add-scc-to-user anyuid -z useroot
```

### Deploy App
```sh
oc apply -f .
```

### Test App
```sh 
oc expose service meteor-tutorial
oc get route
```

visit the url to view the app
