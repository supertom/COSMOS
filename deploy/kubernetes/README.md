# Deploying COSMOS on Kubernetes

## Configuration

1. Set the `DISPLAY` environment variable to the [X Client's](https://en.wikipedia.org/wiki/X_Window_System) IP address and display.
   ```
   export DISPLAY=xxx.xxx.xxx.xxx:0
   ```

## Running

1. Apply the Kubernetes deployment manifest for COSMOS.
   ```
   kubectl apply -f cosmos-deployment.yml
   ```

## Troubleshooting

### Checking deployment status

```
kubectl describe deployments -l app=cosmos
```

### Checking pod status

```
kubectl describe pods -l app=cosmos
```

### Viewing logs

1. Save the pod name. You'll need to do this any time you (re)deploy.
   ```
   export POD_NAME=$(kubectl get pods -l app=cosmos -o go-template --template '{{range .items}}{{.metadata.name}}{{end}}')
   ```

2. View the pod's logs.
   ```
   kubectl logs $POD_NAM
   ```
