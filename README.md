# mysqlcluster
Build a postgres/mysql cluster(1 master, 2 read replicas) in containers

# MySQL Cluster Deployment

This repository contains Kubernetes manifests for deploying a MySQL cluster with one master instance for read and write operations and two replica instances for read-only operations.

## Prerequisites

- Kubernetes cluster configured
- kubectl CLI installed

## Deployment Steps

1. Clone this repository:

   ```bash
   git clone https://github.com/yourusername/mysql-cluster.git
Test code:

bash
Copy code
# Connect to MySQL master (write operations)
mysql -h <MASTER_IP> -u youruser -p

# Connect to MySQL replica (read-only operations)
mysql -h <REPLICA_IP> -u youruser -p


Navigate to the cloned repository:

bash
Copy code
cd mysql-cluster
Apply the Kubernetes manifest:

bash
Copy code
kubectl apply -f mysql-cluster.yaml
Verify the deployment:

bash
Copy code
kubectl get statefulsets
kubectl get pods
kubectl get services
Connect to MySQL master for write operations:

bash
Copy code
mysql -h <MASTER_IP> -u youruser -p
Connect to MySQL replicas for read-only operations:

bash
Copy code
mysql -h <REPLICA_IP> -u youruser -p
Replace <MASTER_IP> and <REPLICA_IP> with the appropriate IP addresses assigned to the master and replica instances respectively.

Configuration
MySQL root password: yourpassword
MySQL database name: yourdatabase
MySQL user: youruser
MySQL user password: yourpassword
Modify these values in the mysql-cluster.yaml file as needed before deploying.

Cleanup
To delete the MySQL cluster, run the following command:

bash
Copy code
kubectl delete -f mysql-cluster.yaml
