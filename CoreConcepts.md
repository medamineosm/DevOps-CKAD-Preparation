# Core Concepts

 - ### Create a namespace called '**mynamespace**' and a pod with image **nginx** called nginx on this namespace
	 - `kubectl create namespace mynamespace`
	 - `kubectl run nginx --image=nginx --restart=never -n mynamespace`
 - ### Create the **pod** that was just described using **YAML**
	 - #### By Command
		-  `kubectl run nginx --image=nginx:latest --restart=never -n mynamespace --dry-run=client -o yaml > pod.yml`
	 - #### By YAML
```yaml
# pod.yml
		apiVersion: v1
		kind: Pod
		metadata:
			namespace: mynamespace
			name: pod-name
		spec:
			containers
			- name: nginx:latest
			  command: ['nginx']
			  args: ['-g','daemon;']
			  ports:
			  - containerPort: 80
```

		- kubectl apply -f pod.yml 
- ### Create a busybox pod (using kubectl command) that runs the command "env". Run it and see the output	
