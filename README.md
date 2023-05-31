# Persistance Volumes:
It act like EBS,EFS in AWS.
In docker we use docker vilumes to store the data,but the thing is if the docker container and node gonns crashes entire data gonna be loat,
so to overcome this k8s store the data in remote location becuease eks cluster ,pod and slave nodee are not perminanet,they gonna crash any time.
Main container continuesly creating logs if we store them in same node,it is not the best practice.
Side car container responsability is to getting the data from Data storage which was created main running container and sending them to elastic search.

# Emty Directory:
Is a type of volume in k8s,Where multiple containers are connected to the Emty directory.
