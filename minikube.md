# **Minikube**

**Minikube**  is an open source tool that was developed to enable developers and system administrators to run a single cluster of Kubernetes on their local machine. Minikube starts a single node kubernetes cluster locally with small resource utilization. This is ideal for development tests.

### Step 1: Update system:

    sudo apt-get update
    
    sudo apt-get install apt-transport-https
    
    sudo apt-get upgrade

### Step 2: Install Docker:

    sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add –
    
    sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable
    
    apt-cache policy docker-ce
    
    sudo apt-get install -y docker-ce
    
    sudo systemctl status docker
    
    docker run -d -p 5000:5000 --restart=always --name registry registry:2 #for local image

### Step 3: Install Minikube:

    sudo wget https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
    
    sudo chmod +x minikube-linux-amd64
    
    sudo mv minikube-linux-amd64 /usr/local/bin/Minikube
    
    minikube version

### Step 4: Install Kubectl:

    curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl
    
    sudo chmod +x ./kubectl
    
    sudo mv ./kubectl /usr/local/bin/kubectl
    
    kubectl version -o json

### **Step 5: Start Minikube:**

    echo ‘export CHANGE_MINIKUBE_NONE_USER=true’ >> ~/.bashrc
    
    minikube start
    
    eval $(minikube docker-env)

### Step 6: Check Status Minikube and Kubectl:

    minikube service list
    
    minikube docker-env
    
    kubectl cluster-info
    
    kubectl config view
    
    kubectl get nodes

### Step 7: Deploy Pod:

    kubectl create deployment test-nginx --image=nginx
    
    Kubectl get pods
    
    kubectl exec pod_name env
    
    kubectl exec -it pod_name bash
    
    kubectl scale deployment test-nginx --replicas=3
    
    kubectl expose deployment test-nginx --type="NodePort" --port 80
    
    kubectl get services test-nginx
    
    minikube service test-nginx –url
