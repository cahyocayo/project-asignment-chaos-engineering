<h1>project-asignment-chaos-engineering</h1> 
To simulate HTTP latency between pods in a Core Network using LitmusChaos, 
you can use the Network Chaos experiments provided by Litmus. 
The pod-network-latency experiment simulates network latency by injecting a delay in the communication between pods.
<br>
<br>

<strong>Apply the Chaos Service Account</strong>
<br>
kubectl apply -f chaos-service-account.yml

<strong>Apply the Chaos Experiment definition</strong>
<br>
kubectl apply -f pod-network-latency-experiment.yml

<strong>Apply the ChaosEngine to trigger the experiment</strong>
<br>
kubectl apply -f chaosengine-network-latency.yml

<strong>Describe the ChaosEngine to view experiment status</strong>
<br>
kubectl describe chaosengine pod-network-latency-chaos -n default

<strong>View the logs of the running chaos experiment</strong>
<br>
kubectl logs -f <chaos-pod-name> -n default

