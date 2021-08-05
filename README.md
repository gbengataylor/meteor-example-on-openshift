# meteor-example-on-openshift
Deploy a meter sample app to openshift (persistence not included)

Question/todo : if a pvc is added will this speed up the meteor run/npm build that the container executes during a restart or redeployment? 

## Optional
Build sample image using https://dockerize.io/guides/docker-meteor-guide.

This repo will be using this image ```quay.io/gbengataylor/meteor-tutorial:1.0```. To use your image that is hosted in a registry, edit meteor-deployment.yaml and replace the image name

## Deploy

### create project
```sh
oc new-project meteor-on-openshift
```

### Create Service Account to run as priviledged container
Note: Only do this if your meteor app needs to run as priviledged. If it doesn't, skip this step and remove the ```serviceAccount``` field from meteor-deployment.yaml
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
oc get route
```

visit the url to view the app
