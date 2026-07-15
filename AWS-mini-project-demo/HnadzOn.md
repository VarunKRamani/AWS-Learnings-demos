# Overview

- This example demonstrates how to create a VPC that you can use for servers in a production environment.
- To improve resiliency, we deploy the servers in two Availability Zones, by using an Auto Scaling group and an Application Load Balancer. For additional security, we deploy the servers in private subnets. 
- The servers receive requests through the load balancer. The servers can connect to the internet by using a NAT gateway. To improve resiliency, we deploy the NAT gateway in both Availability Zones.
- The architecture is created using aws cft. EC2, NAT gateway, internet gateway, elastic ip etc.
- This mini project is to understande how to access a application within a private subnet, with the help of bastion host.

**Auto Scaling group:** Auto scalling group (ASG) in AWS is a service that automatically mantains the desired number of EC2 instnces by launching new instances when the demand increases and replaces unhealthy instances when they fail. It helps ensure high availablity and scalability. 

**NAT Gateway:** NAT Gateway allows an instance in private subnet to access internet (download resources and etc) outbound communication while preventing internet from inbound connection to the instance. 

**Internet Gateway:** An AWS managed gateway that connects VPC with public subnet. It allows traffic to resources in public subnet when appropriate route table and security groups. 

**Elastic IP:** Elastic Ip is nothing but a static IP usually used with resources like instances and NAT gateways. Unlike regular public IPs. elastic IPs attached to the resource remain same, even if the resource restart or is replaced making it useful for stable connectivity. 

**Bastion Host:**
A bastion host also known as a** jump server or jump box** is a highly secured, hardened server specifically designed to act as a secure gateway between an external untrusted network like the public internet and an internal private network.

**Target Group:**
A Target Group is a collection of backend resources (such as EC2 instances, IP addresses, or Kubernetes pods) that receive traffic from a Load Balancer.

**Route Table:**
A Route Table is a set of rules that determines where network traffic from a subnet is directed. Each route specifies a destination (such as another subnet or the internet) and the gateway or resource through which the traffic should be sent.

<img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/8bdd723b-032d-42d6-8496-4855d8135c19" />

## The Architecture
<img width="750" height="500" alt="Screenshot 2026-07-01 195428" src="https://github.com/user-attachments/assets/9f3bbf63-f3f7-4c27-97b1-1a59a7e0e8f0" />

<img width="1457" height="510" alt="image" src="https://github.com/user-attachments/assets/b5066067-f7e3-41bd-822b-c81389ae9870" />
By deploying resources across multiple zones, we ensure that our architecture is robust enough to withstand localized infrastructure disruptions. Using two Availability Zones (AZs) in a production environment is a best practice for improving resiliency and high availability.

_____


- Creation of resources
<img width="1120" height="844" alt="Screenshot 2025-12-03 124706" src="https://github.com/user-attachments/assets/64afd435-4126-4b21-8c38-bb45efbbc209" />


<img width="1915" height="451" alt="Screenshot 2025-12-03 133714" src="https://github.com/user-attachments/assets/d550fa19-49a3-4d50-88f4-0d8bbd1388a4" />

- Auto Scaling group
<img width="1919" height="588" alt="Screenshot 2025-12-03 133658" src="https://github.com/user-attachments/assets/2a7af2fd-6dc7-4600-9a85-4bc2b1d4cba3" />

- Target groups
<img width="1919" height="935" alt="Screenshot 2025-12-03 145555" src="https://github.com/user-attachments/assets/730252c9-589f-40bb-a55c-0430c84125fe" />

- Project accessable.
<img width="1919" height="1079" alt="Screenshot 2025-12-03 151036" src="https://github.com/user-attachments/assets/c59ec024-3665-4c84-a52c-c2d600ae4196" />

## Process of resource creation
<img width="1919" height="1079" alt="Screenshot 2025-12-03 151118" src="https://github.com/user-attachments/assets/46e8d19d-5267-4e61-880c-39161748339b" />

- VPC creatiion: Here we create a public and private subnet in requried two availability zones i.e in `us-east-1a` and `us-east-1b`. The route table are attached with network connection to Internet Gateway.
- Once the VPC is created, we move to crate Auto Scaling group, for which a launch tamplate needs to be created. For Launch template type in name, type of EC2 requried, OS, Select the VPC created and security group. Now select the reated launch template under Auto scalling group creation with name, VPC, AZs and select the group size (min, max and desired).
- Cross check is the EC2 and other resources are created, once confirmed will move to installing the python app on the server (Instance in private subnet).
- 

**Code Explanation** 
---------------------------------
