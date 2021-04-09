Kubectl is a command line tool for controlling Kubernetes clusters
Nodes
$ kubectl get no
$ kubectl get no - o wide
$ kubectl describe no
$ kubectl get no - o yaml
$ kubectl get node -- select or =[ label_name]
$ kubectl get nodes - o
$ kubectl top node [ node_name]
Pods
$ kubectl get po
$ kubectl get po - o wide
$ kubectl describe po
$ kubectl get po - - show-labels
$ kubectl get po - l app=nginx
$ kubectl get po - o yaml
$ kubectl get pod [ pod_name] - o yaml -- export
$ kubectl get pod [ pod_name] - o yaml -- export > nameoffile.yaml
$ kubectl get pods - - field- select ort at us. phase=Running
Namespaces
$ kubectl get ns
$ kubectl get ns - o yaml
$ kubectl describe ns
Deployments
$ kubectl get deploy
$ kubectl describe deploy
$ kubectl get deploy - o wide
$ kubectl get deploy - o yaml
Services
$ kubectl get svc
$ kubectl describe svc
$ kubectl get svc - o wide
$ kubectl get svc - o yaml
$ kubectl get svc - - show-labels
DaemonSets
$ kubectl get ds
$ kubectl get ds - - all - namespaces
$ kubectl describe ds [ daemonset_name] - n [ namespace_name]
$ kubectl get ds [ ds_name] - n [ ns_name] - o yaml
Events
$ kubectl get events
$ kubectl get events - n kube- system
$ kubectl get events - w
Logs
$ kubectl logs [ pod_name]
$ kubectl logs - - since=1h [ pod_name]
$ kubectl logs - - tail =20 [ pod_name]
$ kubectl logs - f - c [ container_name] [ pod_name]
$ kubectl logs [ pod_name] > pod.log
Service Accounts
$ kubectl get sa
$ kubectl get sa - o yaml
$ kubectl get serviceaccount s default - o yaml > . / sa.yaml
$ kubectl replace serviceaccount default - f . / sa.yaml
ReplicaSets
$ kubectl get rs
$ kubectl describe rs
$ kubectl get rs - o wide
$ kubectl get rs - o yaml
Roles
$ kubectl get roles - - all - namespaces
$ kubectl get roles - - all - namespaces - o yaml
Secrets
$ kubectl get secrets
$ kubectl get secrets - - all - namespaces
$ kubectl get secrets - o yaml
ConfigMaps
$ kubectl get cm
$ kubectl get cm -- all - namespaces
$ kubectl get cm -- all - namespaces - o yaml
Ingress
$ kubectl getting
$ kubectl getting - - all - namespaces
PersistentVolume
$ kubectl get pv
$ kubectl describe pv
PersistentVolumeClaim
$ kubectl get pvc
$ kubectl describe pvc
Storage Class
$ kubectl get sc
$ kubectl get sc - o yaml
Multiple Resources
$ kubectl get svc, po
$ kubectl get deploy, no
$ kubectl get all
$ kubectl get all -- all - namespaces Deployments/Namespaces
$ kubectl edit deploy [ deploy_name]
$ kubectl delete deploy [ deploy_name]
$ kubectl expose deploy [ deploy_name] - - port=80 - - type=NodePort
$ kubectl scale deploy [ deploy_name] - - replicas=5
$ kubectl delete ns
$ kubectl edit ns [ ns_name]
Services
$ kubectl edit svc [ svc_name]
$ kubectl delete svc [ svc_name]
Taint
$ kubectl taint [ node_name] [ taint_name]
Labels
$ kubectl label [ node_name] disktype=ssd
$ kubectl label [ pod_name] env=prod
DaemonSets
$ kubectl edit ds [ ds_name] - n kube-system
$ kubectl delete ds [ ds_name]
Service Accounts
$ kubectl edit sa [ sa_name]
$ kubectl delete sa [ sa_name]
Changing Resource Attributes Cordon/Uncordon
$ kubectl cordon [ node_name]
$ kubectl uncordon [ node_name]
Drain
$ kubectl drain [ node_name]
Nodes/Pods
$ kubectl delete node [ node_name]
$ kubectl delete pod [ pod_name]
$ kubectl edit node [ node_name]
$ kubectl edit pod [ pod_name]
Annotate
$ kubectl annotate po [ pod_name] [ annotation]
$ kubectl annotate no [ node_name]
Adding Resources Creating a Pod
$ kubectl create - f [ name_of _file]
$ kubectl apply - f [ name_of _file]
$ kubectl run [ pod_name] -- image=nginx -- restart =Never
$ kubectl run [ pod_name] -- generator =run- pod/ v1 -- image=nginx
$ kubectl run [ pod_name] -- image=nginx -- restart =Never
Creating a Deployment
$ kubectl cr eat e - f [ name_of_file]
$ kubectl apply - f [ name_of_file]
$ kubectl create deploy [ deploy_name] -- image=nginx
Requests - API Call
$ kubectl get -- raw / apis/ metrics. k8s. i o/Cluster Info
$ kubectl config
$ kubectl cluster - info
$ kubectl get component stat uses
Interactive Pod
$ kubectl run [ pod_name] - - i mage=busybox -- rm - it -- restart =Never -- sh Output YAML to aFile
$ kubectl create deploy [ deploy_name- - image=nginx - - dry- run - o yaml > deploy. yaml
$ kubectl get po [ pod_name] - o yaml - - export > pod. yaml
Debugging Commands
$ kubectl logs [ pod_name]
$ kubectl exec -it [ pod_name] --bash
$ kubectl attach -it [ pod-name ]
$ kubectl top nodes
$ kubectl top pods
Getting Help
$ kubectl - h
$ kubectl create - h
$ kubectl run - h
$ kubectl explain deploy. spec
