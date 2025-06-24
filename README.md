# Project-Capstone-Ansible
Team 1: Server Roles and IP Assignments
1. Parviz
Roles: Ansible, Docker (Primary)
Hostnames:
prdx-ansible101 (Ansible VM)
prdx-dprimary101 (Primary Docker VM)
IP Range: 192.168.84.10 – 192.168.84.20
2. Sitora
Roles: Database, Web Server 1
Hostnames:
prdx-db101 (Database Server)
prdx-webserver101 (Web Server 1)
IP Range: 192.168.84.20 – 192.168.84.30
3. Shokhista
Roles: Docker Worker 1, Docker Worker 2, Kubernetes
Hostnames:
prdx-dworker101 (Docker Worker 1)
prdx-dworker102 (Docker Worker 2)
prdx-kube101 (Kubernetes Master/Node)
IP Range: 192.168.84.30 – 192.168.84.40
4. Parvina
Roles: Load Balancer (HAProxy), Monitoring (Nagios)
Hostnames:
prdx-haproxy101 (HAProxy Load Balancer)
prdx-nagios101 (Nagios Monitoring Server)
IP Range: 192.168.84.40 – 192.168.84.50
5. Ziyoda
Roles: Web Server 2, Web Server 3
Hostnames:
prdx-webserver102 (Web Server 2)
prdx-webserver103 (Web Server 3)
IP Range: 192.168.84.50 – 192.168.84.60


#1Step
Passwordless ssh for all servers
