# Docker Kubernetes & OpenShift - IBM Lab Exercises 

This repository contains the materials for four labs on Docker, Kubernetes, and OpenShift.

## Lab 1: Docker Basics

### Objectives
- Pull an image from Docker Hub.
- Run an image as a container.
- Build and tag an image using a Dockerfile.
- Push the image to a registry.

### Commands
```bash
docker pull <image-name>
docker run -d <image-name>
docker build -t <your-tag>:<version> .
docker push <your-tag>:<version>
```


## Lab 2: Kubernetes Basics

### Objectives
- Create a ReplicaSet.
- Create a Kubernetes Pod using different methods.
- Use the `kubectl` CLI.
- Tested commands to create and delete Pods and ReplicaSets.

### Commands
```bash
kubectl create -f replicaset.yaml
kubectl run <pod-name> --image=<image-name>
kubectl create -f pod.yaml
kubectl apply -f pod-declarative.yaml
```

## Lab 3: Kubernetes Application Management (Scaling & Updating)

### Objectives
- Scale and update applications.
- Scale an application with a ReplicaSet.
- Apply rolling updates to an application.
- Use a ConfigMap to store application configuration.
- Autoscale the application using Horizontal Pod Autoscaler.

### Commands
```bash
kubectl scale --replicas=<number> deployment/<deployment-name>
kubectl set image deployment/<deployment-name> <container-name>=<new-image>
kubectl rollout undo deployment/<deployment-name>
kubectl create configmap <configmap-name> --from-file=<path/to/config>
kubectl autoscale deployment/<deployment-name> --min=<min-pods> --max=<max-pods> --cpu-percent=<percentage>
```

## Lab 4: OpenShift Basics

### Objectives
- Use the `oc` CLI (OpenShift command line interface).
- Use the OpenShift web console.
- Build and deploy an application using s2i (‘Source-to-image’ build strategy).
- Inspect a BuildConfig and an ImageStream.
- Autoscale the application.

### Commands
```bash
oc login <server> --token=<token>
oc new-project <project-name>
oc new-app <source-repo-url>
oc start-build <buildconfig-name>
oc get builds
oc describe build <build-name>
oc get imagestreams
oc autoscale dc/<deploymentconfig-name> --min=<min-pods> --max=<max-pods> --cpu-percent=<percentage>
