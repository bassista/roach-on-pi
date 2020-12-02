# roach-on-pi
Scripts needed to build and deploy CockroachDB on a Raspberry PI K8s cluster 

code for "Deploying CockroachDB on a Raspberry Pi’s Kubernetes cluster" post
https://medium.com/@marceloglezer/cockroachdb-on-a-raspberrypi-kubernetes-cluster-7b12a2e497e1

Now updated to version 20.2.0

git clone git@github.com:gato/roach-on-pi.git
cd roach-on-pi
kubectl apply -f cockroachdb-statefulset.yaml

kubectl get pods
until you get all pods with STATUS in Running
NAME            READY     STATUS    RESTARTS   AGE
cockroachdb-0   0/1       Running   0          2m
cockroachdb-1   0/1       Running   0          2m
cockroachdb-2   0/1       Running   0          2m

Run one-time initialization
kubectl create -f cluster-init.yaml

check again
kubectl get pods
