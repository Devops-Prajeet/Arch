# Arch

              Users
                |
         ┌───────────────────┐
         │  Load Balancer    │
         └───────────────────┘
                |
    ┌──────────────────────────┐
    │   Virtual Machine Pool    │  (Multiple VMs for Redundancy) (4VCPU,x86_64 (REDHAT),8GB RAM)
    │ ┌───────┐  ┌───────┐  ┌───────┐ │
    │ │  VM1  │  │  VM2  │  │  VM3  │ │
    │ │ Vault │  │ Vault │  │ Vault │ │
    │ └───────┘  └───────┘  └───────┘ │
    └──────────────────────────┘
                |
   ┌────────────────────────────┐
   │ High Availability Database │
   │(Master-Slave or Multi-Primary) │
   └────────────────────────────┘
                |
   ┌──────────────────────────┐
   │ Shared Storage (NFS,EFS) │
   └──────────────────────────┘
                |
   ┌──────────────────────────┐
   │    Monitoring & Security │ (Prometheus, Grafana)
   └──────────────────────────┘

---

Highly Available Virtual Machine (VM) Architecture
Key Components
Multiple VM Instances: Run multiple VMs across different physical servers or availability zones. (Proxmox, VMware ESXi, or OpenStack for VM clustering)
Load Balancer: Distributes traffic between VM instances.
High Availability Storage: Use shared storage like NFS.
Failover & Auto Recovery: Automate failover using clustering techniques.
Database Replication: Set up database replication across VMs for redundancy.
Monitoring & Security: Implement monitoring tools like Prometheus/Grafana.
