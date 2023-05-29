By default there is no load balancer in Docker.
# Task :- We need to configur one web to two user containers, how do you do?
We need communication between two containers for that pupose we use 
# Service :-
To talk two pods each other , we can configure IP Adress with each other, but the problem is when you restart the pod there is no garrenty that same IP address will come. So for that purpose we use * **Service** 
First we need to create one service than attach it to the user pod.So now web should call the service it act like load balancing. 
In future we need another user , at that time the another pod is call same service.
K8s service uses for mostly load balancing puposes.
By using labels and selectors service gonna works


