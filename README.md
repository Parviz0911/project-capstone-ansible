CONFIG FILE 
Host db1
    HostName 192.168.84.20
    User root
    le prdx-dprimary101

Host dworker1
    HostName 192.168.84.30
    User root
    IdentityFile prdx-dworker101

Host dworker2
    HostName 192.168.84.36
    User root
    IdentityFile prdx-dworker102

Host kube1
    HostName 192.168.84.33
    User root
    IdentityFile prdx-kube101

Host dns1
    HostName 192.168.84.40
    User root
    IdentityFile prdx-dns101

Host dns2
    HostName 192.168.84.45
    User root
    IdentityFile prdx-dns102

Host ansible1
    HostName 192.168.84.10
    User root
    IdentityFile prdx-ansible101zz



#1Step
Passwordless ssh for all servers
