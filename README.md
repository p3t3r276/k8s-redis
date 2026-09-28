# K8s Template for Redis

## Initialize the environment
- `minikube start` — Starts your local Kubernetes cluster.

## Apply the manifest
- `kubectl apply -f redis-deploy.yaml` — Deploys the Redis instance and its internal service.

## Verify the resources
- `kubectl get deployments` — Checks the deployment status.
- `kubectl get pods` — Verifies that your Redis pod is running.
- `kubectl get service redis-service` — Confirms the ClusterIP internal routing service is active.

## Test the connection inside the cluster
- `kubectl exec -it deploy/redis-deployment` -- redis-cli ping — Sends a test command directly inside the container; it should return PONG.

## Connect from your local host machine (Optional)
- `kubectl port-forward svc/redis-service 6379:6379` — Forwards the traffic so you can interact with Redis using a local desktop GUI tool or script at `127.0.0.1:6379`.

## Stop
- `minikube stop` — Powers down the local Kubernetes node safely.

## Tear Down
- `kubectl delete -f redis-deploy.yaml` — Removes the deployment, pods, and service instantly.
