# RBAC:- Roll Based Access Control.
In real time we dont get admin access.
K8s Admin gonna create cluster and give us a namespace.
Admin gonna creates a role for us. 
They will bind the roles with permissions(Giving)
# Authentication -->Handiled by IAM
# Athorization --> Handled by EKS Cluster
First we need to create IAM role and give athentication to EKS Cluster.(Admin have Read abd list access)
# User --> username and password
# Role --> What are the permissions he had
# Binding --> Admin  gonna attach user with role.
