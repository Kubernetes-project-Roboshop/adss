While pod defination we gonna apply the labels to the node.
# Why do need to do give Labels:
if you have thre tier architecture and you wannt some pods to talk Database only at the time ,we need to give labels so that it those pods going to that particular nodes.
First we need to give lables to nodes by using a command 
 <kubectl labels nodes <node name> <key=value>>
 TO SEE 
 <kubecl get nodes --show-lables>

 # Affinity, Non-affinity:
 =========================
Here we gonna get more controll during scedulling the pods.