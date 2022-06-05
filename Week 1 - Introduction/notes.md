# MLOps Zoomcamp

## Week 1 
###### Overview
1. Learned about MLops
2. Started a Linux_x_86_64 EC2 instance on AWS, installed Anaconda, docker on linux machine and connected to it from VS code using remote ssh
3. Learned about various MLops Maturity models
4. Homework- trained a linear regression model on NYC taxi data

###### Now in detail

##### 1. What is MLops?
![](https://databricks.com/wp-content/uploads/2021/12/MLOps-Cycle.png)
Machine Learning operations is the process of taking the machine learning model from training to deployment (or production) and then maintaining and monitoring them. 

Benefits of MLops:
- Allows faster model development
- Faster deployment
- Continuous Integration / Continuous delivery of models
- **Provides reproducibility of ML pipelines**

Readings - https://databricks.com/glossary/mlops

##### 2. Environment Setup

- Create an EC2 instance on AWS
    Instance type 
    - `ubuntu x86_64`
    - `t2.xlarge`
- Connect to EC2 instance using Terminal 
```
ssh -i ~/.ssh/aws-m1.pem ubuntu@xx.xx.xxx.xxx
#use EC2 ipv4 public address
```
- To connect it easily next time, edit `.ssh/config` file

```yaml
Host mlops-zoompcamp
        HostName <your ip address>
        User ubuntu
        IdentityFile ~/.ssh/<your ssh key>
        StrictHostKeyChecking no
```
This way we don’t have type everything next time. Just type `ssh mlops-zoomcamp`.

- Update package manager `sudo apt update`
- Now, access the ubuntu machine by typing
```
ssh mlops-zoomcamp
```

- Install anaconda on machine
```
wget https://repo.anaconda.com/archive/Anaconda3-2022.05-Linux-x86_64.sh
```

- Install docker
```
sudo apt install docker.io
```

- Install latest docker-compose 
    - First create a directory `mkdir soft`
    - change to soft `cd soft`
    - install docker compose by running
```
wget https://github.com/docker/compose/releases/download/v2.5.1/docker-compose-linux-x86_64 -O docker-compose
```
- Make docker-compose executable `chmod +x docker-compose`

- Modify PATH to access soft from any location. To do that edit ~/.bashrc `nano ~/.bashrc` and add this line

```bash
export PATH="${HOME}/soft:${PATH}”
```

- Refresh bashrc `source ~/.bashrc`

- To check `docker-compose` from any location. Or you can ask which docker-compose it will use `which docker-compose`

- Add user to the docker user group to avoid sudo
```
sudo usermod -aG docker $USER
```
- Now you can run docker `docker run hello-world`

- Clone the mlops-zoomcamp repo in ubuntu machine
```
git clone https://github.com/DataTalksClub/mlops-zoomcamp.git`
```

- To access this machine using VS code, install “Remote-SSH” extension in VS Code. After it is installed, on the bottom left, click the icon looks like ><. Connect the mlops-zoomcamp host

- To access Jupyter notebok in remote machine, type in terminal with ubuntu connection
```
jupyter notebook
``` 

- Go to VSCode and forward a port. It is done on Ports tab in terminal window in VSCode.


##### 3. MLops Maturity models
(https://docs.microsoft.com/en-us/azure/architecture/example-scenario/mlops/mlops-maturity-model)

##### 4. Homework
Assignment: https://github.com/DataTalksClub/mlops-zoomcamp/blob/main/01-intro/homework.md

Solution notebook 


