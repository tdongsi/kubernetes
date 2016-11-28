`kubectl` is the CLI client of Kubernetes. Some example `kubectl` commands are:

```
mymac:my-cluster tdongsi$ kubectl get componentstatuses
NAME                 STATUS    MESSAGE              ERROR
controller-manager   Healthy   ok
scheduler            Healthy   ok
etcd-0               Healthy   {"health": "true"}

mymac:my-cluster tdongsi$ kubectl get nodes
NAME                                       STATUS                     AGE
ip-10-0-0-182.us-west-2.compute.internal   Ready                      5d
ip-10-0-0-183.us-west-2.compute.internal   Ready                      5d
ip-10-0-0-184.us-west-2.compute.internal   Ready                      5d
ip-10-0-0-185.us-west-2.compute.internal   Ready                      5d
ip-10-0-0-50.us-west-2.compute.internal    Ready,SchedulingDisabled   5d

mymac:my-cluster tdongsi$ kubectl describe nodes ip-10-0-0-50.us-west-2.compute.internal
Name:			ip-10-0-0-50.us-west-2.compute.internal
Labels:			beta.kubernetes.io/arch=amd64
			beta.kubernetes.io/instance-type=m3.medium
			beta.kubernetes.io/os=linux
			failure-domain.beta.kubernetes.io/region=us-west-2
			failure-domain.beta.kubernetes.io/zone=us-west-2a
			kubernetes.io/hostname=ip-10-0-0-50.us-west-2.compute.internal
Taints:			<none>
CreationTimestamp:	Mon, 21 Nov 2016 14:22:37 -0800
Phase:
...

mymac:my-cluster tdongsi$ kubectl get pods
mymac:my-cluster tdongsi$ kubectl get pods --namespace=spinnaker
NAME                           READY     STATUS    RESTARTS   AGE
data-redis-master-v000-r4tsy   1/1       Running   0          4d
spin-clouddriver-v000-7ht8k    1/1       Running   0          4d
spin-deck-v000-5men3           1/1       Running   0          4d
spin-echo-v000-ippzy           1/1       Running   0          4d
spin-front50-v000-dqtcb        1/1       Running   0          4d
spin-gate-v000-sglkm           1/1       Running   0          4d
spin-igor-v000-j06zg           1/1       Running   0          4d
spin-orca-v000-ia83e           1/1       Running   0          4d


mymac:my-cluster tdongsi$ kubectl get services --namespace=spinnaker
NAME                CLUSTER-IP   EXTERNAL-IP   PORT(S)    AGE
data-redis-server   10.3.0.237   <none>        6379/TCP   4d
spin-clouddriver    10.3.0.23    <none>        7002/TCP   4d
spin-deck           10.3.0.209   <none>        9000/TCP   4d
spin-echo           10.3.0.107   <none>        8089/TCP   4d
spin-front50        10.3.0.253   <none>        8080/TCP   4d
spin-gate           10.3.0.58    <none>        8084/TCP   4d
spin-igor           10.3.0.220   <none>        8088/TCP   4d
spin-orca           10.3.0.52    <none>        8083/TCP   4d

mymac:my-cluster tdongsi$ kubectl get services
NAME         CLUSTER-IP   EXTERNAL-IP   PORT(S)   AGE
kubernetes   10.3.0.1     <none>        443/TCP   5d
```
