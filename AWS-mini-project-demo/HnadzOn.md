# Overview

- This example demonstrates how to create a VPC that you can use for servers in a production environment.
- To improve resiliency, we deploy the servers in two Availability Zones, by using an Auto Scaling group and an Application Load Balancer. For additional security, we deploy the servers in private subnets. 
- The servers receive requests through the load balancer. The servers can connect to the internet by using a NAT gateway. To improve resiliency, we deploy the NAT gateway in both Availability Zones.
- The architecture is created using aws cft. EC2, NAT gateway, internet gateway, elastic ip etc.
- This mini project is to understande how to access a application within a private subnet, with the help of bastion host.

Auto Scaling group:
NAT Gateway:
Internet Gateway:
Elastic IP:
**Bastion Host:**
A bastion host also known as a** jump server or jump box** is a highly secured, hardened server specifically designed to act as a secure gateway between an external untrusted network like the public internet and an internal private network.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/8bdd723b-032d-42d6-8496-4855d8135c19" />

## The Architecture
<img width="750" height="500" alt="Screenshot 2026-07-01 195428" src="https://github.com/user-attachments/assets/9f3bbf63-f3f7-4c27-97b1-1a59a7e0e8f0" />
_____
- Creation of resources
<img width="1120" height="844" alt="Screenshot 2025-12-03 124706" src="https://github.com/user-attachments/assets/64afd435-4126-4b21-8c38-bb45efbbc209" />

- Instances created on different avilablity zones through AWS Cloud Formation, And Bastion Host.
<img width="1915" height="451" alt="Screenshot 2025-12-03 133714" src="https://github.com/user-attachments/assets/d550fa19-49a3-4d50-88f4-0d8bbd1388a4" />

- Auto Scaling group
<img width="1919" height="588" alt="Screenshot 2025-12-03 133658" src="https://github.com/user-attachments/assets/2a7af2fd-6dc7-4600-9a85-4bc2b1d4cba3" />

- Target groups
<img width="1919" height="935" alt="Screenshot 2025-12-03 145555" src="https://github.com/user-attachments/assets/730252c9-589f-40bb-a55c-0430c84125fe" />

- Project accessable.
<img width="1919" height="1079" alt="Screenshot 2025-12-03 151036" src="https://github.com/user-attachments/assets/c59ec024-3665-4c84-a52c-c2d600ae4196" />

- Exp ---------------------
<img width="1919" height="1079" alt="Screenshot 2025-12-03 151118" src="https://github.com/user-attachments/assets/46e8d19d-5267-4e61-880c-39161748339b" />

