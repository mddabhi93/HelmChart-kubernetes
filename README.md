# HelmChart-kubernetes
Kubernetes Cluster Deployment using Helm Chart


Helm Chart Deployment using kubernetes
Step-1:- Install Docker
sudo apt install docker.io
sudo usermod -aG docker $USER
sudo chmod 666 /var/run/docker.sock
sudo systemctl daemon-reload
sudo systemctl start docker.service

Step-2:- Install Kubectl
curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s
https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd6
4/kubectl
chmod +x ./kubectl
sudo mv ./kubectl /usr/local/bin/kubectl
kubectl version --client

Step-3:- Install minikube

curl -Lo minikube
https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 \
&& chmod +x minikube \
&& sudo mv minikube /usr/local/bin/
● sudo -i
● minikube start --driver=none
● minikube status


Step 4: Create Amazon Public Elastic Container
Registry

Step 5: Create a New Helm Chart

helm create <chart name>
ls <chart name>● Give push commands :-

1.Retrieve an authentication token and authenticate your Docker client to your registry.
Use the AWS CLI:
aws ecr-public get-login-password --region us-east-1 | docker login --username AWS
--password-stdin public.ecr.aws/u3p6z1h2

2.Build your Docker image using the following command. Build your Docker image using
the following command.
docker build -t node-app .

3. After the build completes, tag your image so you can push the image to this
repository:
docker tag node-app:latest public.ecr.aws/u3p6z1h2/node-app:latest

4. Run the following command to push this image to your newly created AWS
repository:
docker push public.ecr.aws/u3p6z1h2/node-app:latest

Step 5: Configure Helm Chart Image Pull Policy

1. Open the values.yaml file in a text editor. Locate the image values:
2. Give tag latest have we use ECR:Step 6: Helm Chart Name Override
Step 7: Specify Service Account NameStep 8: Change Networking Service Type
Step 9: Open deployment.yaml change container
port and remove liveness and readiness:

Deploy Helm Chart
Step 1: Check minikube Status
1. Check Minikube status with:
minikube status
2. If the status shows Stopped, 
run:
minikube start
Step 2: Install the Helm Chart
Install the Helm chart using the helm install command:
helm install <full name override> <chart name>/ --values <chart name>/values.yaml

Step 3: Export the Pod Node Port and IP Address
1. Copy the two export commands from the helm install output.
2. Run the commands to get the Pod node port and IP address:

Step 4: View the Deployed Application
1. Copy and paste the echo command and run it in the terminal to print the IP address and
port:2. Copy the link and paste it into your browser, or press CTRL+click to view the deployed
application:
