## 1 “Basics of working with Kubernetes”

### Goal: Create a minimal service

- responds on port 8000
- has an http method GET `/health/` RESPONSE: `{"status": "OK"}`
- url where you can get a response from the service (or a test in Postman)
- Task with a star* (+5 points):
     - In Ingress there should be a rule that forwards all requests from `/otusapp/{student name}/*` to the service with
       rewrite path. Where `{student name}` is the student's name.
- Build a local application image in Docker
- Push the image to Dockerhub
- Write manifests for deployment in k8s for this service
- Manifests must describe the Deployment, Service, Ingress entities
- Liveness, Readiness samples can be specified in Deployment
- The number of replicas must be at least 2
- The container image must be provided from Dockerhub
- The host in the ingress must be `arch.homework`
- As a result, after applying GET manifests, a request to `http://arch.homework/health` should return `{“status”: “OK”}`.


### Startup instructions

- Manifests should be in the same directory so that they can all be applied with one command.

```shell
kubectl apply -f deployment.yaml -f service.yaml -f ingress.yaml
```