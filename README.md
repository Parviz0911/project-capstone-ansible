

**DevOps Project – Full Instructions & Explanation**

**Overview:**
This project simulates a real-world DevOps workflow using ESXi, Ansible, DNS, Apache, HAProxy, MariaDB, Nagios, Docker Swarm, Kubernetes, Jenkins, and AWS with Terraform & CI/CD. It covers:

1. On-Premises Virtualization (ESXi)
2. Configuration Management & Automation (Ansible)
3. Web Hosting & Load Balancing (Apache + HAProxy)
4. Database Setup (MariaDB)
5. Monitoring & Alerts (Nagios)
6. Containerization & Orchestration (Docker Swarm & Kubernetes)
7. CI/CD Pipeline (Jenkins + GitHub + DockerHub)
8. Cloud Deployment (AWS via Terraform)

---

**Infrastructure:**

* **On-Premises with ESXi**:

  * Web Server 1 (192.168.12.18) – Apache
  * Web Server 2 (192.168.12.19) – Apache
  * Load Balancer (192.168.12.20) – HAProxy
  * Database Server – MariaDB
  * Monitoring Server – Nagios

* **Automation & Containers:**

  * Ansible: Install & configure servers automatically
  * Docker & Swarm: Containerize & replicate apps
  * Kubernetes: Deploy apps with pods, services, ingress, and persistent storage

* **Cloud & CI/CD:**

  * Terraform: Create AWS EC2, VPC, Subnets, and Load Balancer
  * Jenkins: GitHub integration, Docker image build, push to DockerHub, deploy to K8s
  * Nagios: Monitor server health and send alerts

---

**Step-by-Step Instructions:**

**1. Setup Virtual Machines on ESXi**

* Create VMs: Web1, Web2, LB, DB, Nagios
* Assign IPs according to plan (192.168.12.xx)

---

**2. Configure Ansible**

```bash
# 1. Setup inventory file
[webservers]
192.168.12.18
192.168.12.19

[loadbalancer]
192.168.12.20

# 2. Test connectivity
ansible all -m ping
```

* Playbooks will install Apache, HAProxy, MariaDB and deploy the web page.

---

**3. Configure HAProxy (Load Balancer)**

```bash
# /etc/haproxy/haproxy.cfg
frontend http_front
    bind *:80
    default_backend web_servers

backend web_servers
    balance roundrobin
    server web1 192.168.12.18:80 check
    server web2 192.168.12.19:80 check
```

* Restart HAProxy and test load balancing.

---

**4. Setup MariaDB (Database Server)**

```bash
sudo yum install mariadb-server -y
sudo systemctl start mariadb
sudo mysql_secure_installation
```

* Create a database and user for the web app.

---

**5. Deploy Docker & Docker Swarm**

```bash
# On Manager Node
docker swarm init --advertise-addr 192.168.12.18

# On Worker Nodes
docker swarm join --token <TOKEN> 192.168.12.18:2377

# Deploy service
docker service create --name web --replicas 3 -p 80:80 nginx
```

---

**6. Deploy Kubernetes**

```bash
kubectl create namespace devops
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
```

* Use ConfigMaps and Persistent Volumes for data storage.

---

**7. CI/CD Pipeline in Jenkins**

1. Install Jenkins + Docker + K8s plugins.
2. Create a pipeline:

   * Pull code from GitHub
   * Build Docker image
   * Push to DockerHub
   * Deploy to Kubernetes cluster

---

**8. Terraform for AWS**

```bash
provider "aws" {
  region = "us-east-1"
}

resource "aws_instance" "web" {
  ami           = "ami-0c02fb55956c7d316"
  instance_type = "t2.micro"
}
```

* Run: `terraform init`, `terraform plan`, `terraform apply`

---

**9. Nagios Monitoring**

* Install Nagios Core.
* Add hosts: Web, DB, LB servers.
* Configure service checks for CPU, disk, and service uptime.
* Setup email alerts for downtime.

---

**Project Deliverables:**

1. Architecture diagram
2. Ansible playbooks
3. HAProxy config
4. Docker/K8s manifests
5. Terraform files
6. Jenkins pipeline script
7. Nagios screenshots



If you want, I can also **make a single-page architecture diagram** to include in your presentation.
Do you want me to create that? It will make your project **look professional**.
