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

# Storage  outside of the k8s:
Just like external hard disk 
We can it as persitance volume: PV, 
# Persistance volume claim:
# Static provisioning
K8s managing extenal storage by using persistance volume and persistance volume claim.
<k8s>----> <PV, PVC>---> <External Storage>
pv gonna declare the storage and pvc gonna declare the

# Fisrt need to  create one PV , then PVC gonna claiming the PV
# Pods gonna claim the PV by using PVC.

Bassically pods gonna ask for storage to the PVC and then pvc will ask the pv.
Then pv gonna check the External storage and send fetch the storage,
PVC rewquesting or claiming to the PV for storage.

### <K8s life scycle policies>
# Reatin: Even the running pod is removed or crashed k8s autoamtically retain the Data, it will make sure the  to remove the data along with POD.
# Delete: Even pod deleted or replaced by amother pod , by default data  will be deleted but when configure persistace volumes and claims ,we gonna separate the data from pods.

# So to ensure the data : We need to configure the pod to the PCV and make sure the pcv is associated with PVC, 

# Acces mode:
RWO: Read write once: At a time only one node can be modify.
RWM: Read write mamy: We can modify many pods in node at a time.
RO: Read Only.
# Static Provisioning and Dynamic Provisioning:
Static we need to proviion manually, Dynamic we PVs atuomatically provison.


