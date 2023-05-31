# ReplicaSet responsability is ensuring the number of replicas running at all the give time.
# ReplicaSets automatically replace,remove unhealthy and inactive pods.
# Replicasets are  also responsable for workload scalling and high availability of PODs.
# ReplicaSets controller by default creates 3 replicas. if one fails another will be created and running.
#  ReplicaSets monitor the health of Pod replicas. If a Pod fails or is terminated for any reason, the ReplicaSet
 #automatically replaces it with a new one to maintain the desired number of replicas. This self-healing capability 
 #ensures high availability of your application.
# ReplicaSets facilitate rolling updates of your application. When you need to update the application image or configuration, you can create a new ReplicaSet with the updated specifications. The ReplicaSet controller gradually replaces the old Pods with the new ones,
 #ensuring a smooth transition without any downtime.
Integration with other Kubernetes Objects: ReplicaSets are often used in conjunction with other Kubernetes 
#objects. For example, you can create a Service to expose your ReplicaSet as a stable endpoint, 
#or use a Deployment to manage the ReplicaSet's lifecycle and rolling updates.

<Managing Replicas:> <Scaling> <Self-Healing> <Rolling Updates:> 
K8s gonna make application highly scalable,high availabile and fault tolerence by using controller manager and replicasets
Rel=plicates gonna scale the desired no of pods.
Replicasets gonna maintain pod's lifecycle and rolling updates.

# Problem with ReplicaSets:
=============================
When you want to update a new version of deocker image, you need to remove the old one.
Replicasets is unable to update the new version of image.
When ever you release the new version of Application,you need to remove the replicaSet and create the new replicaset.

# To resolve this problem we have new concept of Deployment. 
Once we deploy the Application, Whenever the ew version need to deploy then deployment automatically update the new version.
<kubectl get rs>
pod is subcet of replicaset and replicaset is subset of Deployment.
Deployment is highest objenct to deploy the pods.
Deployment is managing pods by using REPLICASETS.

# Rolling Updates:-
=================
While rolling updates we need to maintain <Zero time>,
While Updating the new version , Deployment should need to maintain zero down time and update the aplication at a time.
Example for rolling updates:
When 10 pods are running we need to create 11 one and then remove 10 one.
Deployment will create new poda and remove the existing old pod.
Offcourse at the new release time we see two APPLICATIONS running but we won't get any imapct on our business.
<Even we can overcome this problem by using rolling update strategy>
