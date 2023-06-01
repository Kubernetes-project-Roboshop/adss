# Persistance Volumes:
It act like EBS,EFS in AWS.
In docker we use docker vilumes to store the data,but the thing is if the docker container and node gonns crashes entire data gonna be loat,
so to overcome this k8s store the data in remote location becuease eks cluster ,pod and slave nodee are not perminanet,they gonna crash any time.
Main container continuesly creating logs if we store them in same node,it is not the best practice.
Side car container responsability is to getting the data from Data storage which was created main running container and sending them to elastic search.

# Emty Directory and Host path:
Is a type of volume in k8s,Where multiple containers are connected to the Emty directory.
Mounting config maps as volumes:
create config maps for files like nginx.config.
mount them as volumes
use it for containers

# Host path
It is a type of volume ,we is used to acces the filesystem undelying node file sysytem. thriugh the container.
We use it for the daemon set purpose.


# Daemon Set:
Daemon set responsable for runs pod in each and every node for logs .var/log
it will shoft the metrics to the elastic search.
A DaemonSet is used when you need to run a copy of a pod on each node in a cluster, guaranteeing that there is exactly one instance of the pod running on each node. This is particularly useful for tasks such as monitoring agents, log collectors, or networking proxies that require running on every node.

When you create a DaemonSet, Kubernetes automatically creates and manages the pods on each node. If a new node is added to the cluster, a pod will be scheduled on that node, and if a node is removed, the pod running on it will be terminated.



