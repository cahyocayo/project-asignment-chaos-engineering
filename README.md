# project-asignment-chaos-engineering
To simulate HTTP latency between pods in a Core Network using LitmusChaos, 
you can use the Network Chaos experiments provided by Litmus. 
The pod-network-latency experiment simulates network latency by injecting a delay in the communication between pods.

# Apply the Chaos Service Account
kubectl apply -f chaos-service-account.yml

# Apply the Chaos Experiment definition
kubectl apply -f pod-network-latency-experiment.yml

# Apply the ChaosEngine to trigger the experiment
kubectl apply -f chaosengine-network-latency.yml

# Describe the ChaosEngine to view experiment status
kubectl describe chaosengine pod-network-latency-chaos -n default

# View the logs of the running chaos experiment
kubectl logs -f <chaos-pod-name> -n default

