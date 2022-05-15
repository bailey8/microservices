## Start app locally

### Change the host file

1. add entry in hosts file so the prod posts.com URL gets resolved to localhost
   1. host file on windows	`C:\Windows\System32\drivers\etc`
   2. host file on mac        `/etc/hosts`
   3. Add this line: `127.0.0.1 posts.com`

### Start up kubernetes resources

1. `cd infra/k8s`
2. Add all the resources
   1. `kubectl apply -f client-depl.yaml`
   2. `kubectl apply -f comments-depl.yaml`
   3. `kubectl apply -f event-bus-depl.yaml`
   4. `kubectl apply -f ingress.yaml`
   5. `kubectl apply -f moderation-depl.yaml` 
   6. `kubectl apply -f posts-depl.yaml`
   7. `kubectl apply -f posts-srv.yaml`
   8. `kubectl apply -f query-depl.yaml`
3. Tear down resources
   1. `kubectl delete -f client-depl.yaml`
   2. `kubectl delete -f comments-depl.yaml`
   3. `kubectl delete -f event-bus-depl.yaml`
   4. `kubectl delete -f ingress.yaml`
   5. `kubectl delete -f moderation-depl.yaml` 
   6. `kubectl delete -f posts-depl.yaml`
   7. `kubectl delete -f posts-srv.yaml`
   8. `kubectl delete -f query-depl.yaml`

### View app

Go to `posts.com` in browser and the react app should be there

### How to make a change to the code

1.  Make change to code
2.  Rebuild your image with:    `docker build . -t bailey8/imageName`
3.	Push updated image to docker hub:   `docker push bailey8/imageName`
4.	Restart deployment to use this new image:   `k rollout restart deployment <deploymentName>`







