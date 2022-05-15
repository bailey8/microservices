## Start app locally

### Change the host file

1. add entry in hosts file so the prod posts.com URL gets resolved to localhost
   1. host file on windows	`C:\Windows\System32\drivers\etc`
   2. host file on mac        `/etc/hosts`
   3. Add this line: `127.0.0.1 posts.com`

### Start up kubernetes resources

1. `skaffold dev`
   1. This will load every resource in `infra/k8s` into the cluster
   2. `ctrl+c` to tear down everything

### View app

Go to `posts.com` in browser and the react app should be there

### How to make a change to the code

1.  Skaffold sends changes automatically to your pods
2.  If hot reloading is enabled in the pod app then you will see the change (like nodemon)







