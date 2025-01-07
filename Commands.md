1. kubectl get nodes - to get no. of nodes
2. minikube start - to start minikube 
3. minikube start --memory=4096 --driver=hyperkit - for big application 
4. kubectl create -f pod.yml - to create pod
5. kubectl get pods - to get details about pod
6. kubectl get pods -o wide - to get detailed info about pods
7. minikube ssh - to login into kubernetes cluster, curl <ip_address of pod> - to run the application


//use kubernetes cheatsheet to get bunch of kubernetes commands