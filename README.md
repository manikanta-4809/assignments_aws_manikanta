# assignments_aws_manikanta

### Deploying a Secure, Public Web Server on AWS

1.Creating a Key Pair

<img width="942" alt="image" src="https://github.com/user-attachments/assets/132bcbdd-4a48-49d6-b30b-68f14f386ad5" />

2.Creating VPC

![Screenshot (3)](https://github.com/user-attachments/assets/dc402704-5c0c-44da-9490-2bf205c631ed)

3.Creating Public Subnet

![Screenshot (4)](https://github.com/user-attachments/assets/1dea9cec-60ec-4d5e-a5a7-2dbf7b829760)

4.Creating a Internet Gateway

![Screenshot (5)](https://github.com/user-attachments/assets/73f49893-26c0-4d1b-b68a-8d126d5b9f77)

5.Creating a Public Route Table

![Screenshot (6)](https://github.com/user-attachments/assets/5a7e213d-ae0e-4d18-b978-5e38870b516f)

6.Craeting a Security Group

![Screenshot (8)](https://github.com/user-attachments/assets/f545bc16-4982-4bd5-8cff-d77a355fbd85)

7.Launching EC2 Instance

![Screenshot (9)](https://github.com/user-attachments/assets/8c1d7b15-78d1-45b9-8104-7d2cacce3b50)

![Screenshot (13)](https://github.com/user-attachments/assets/b90924b0-e506-4e96-86bc-339ff559b123)

8.Accessing the Public in Browser

![Screenshot (10)](https://github.com/user-attachments/assets/bf553772-b043-4f23-a5ab-f23128a060ed)
9.vpc resource map

![Screenshot (12)](https://github.com/user-attachments/assets/8e98e539-118d-41f6-ad66-407893971044)


## EXPLANATION
First creating a key pair named KP to securely access my ec2 instance via ssh,making sure to save the private key safely. Then,i set up a custom vpc to keep my resources organized and isolated. Inside the vpc,i created a public subnet, configuring it to automatically assign public ip to any instances i launch there. Next,i built an internet gateway and attached it to my vpc,enabling internet connectivity. To route traffic,i crafted a public route table, added a route directing all outbound traffic to the internet gateway,and linked it to my public subnet.After that,i created  a security group to control access, allowing http traffic for web access and ssh for secure connections.In the AWS vpc console,i checked the resource map to confirm that my vpc,subnet,internet gateway,and route table were all connected perfectly.Then,i launched an ec2 instance in my public subnet,selecting my KP key pair,the public subnet,and the security group i created.i enabled auto-assign public ip and added a user data script to install Apache and serve a custom webpage with a message. Once the instance was running,i used public ip and opened site in my browser—using http since i dont have acces to https port.My webpage loaded successfully.

### Building a Two-Tier Web Application Infrastructure

1.Creating a VPC named two-tier-vpc

![Screenshot (15)](https://github.com/user-attachments/assets/1e1da4ca-ca86-45d1-a5c8-4c60935176d7)

2.Creating Public and Private Subnet

![Screenshot (19)](https://github.com/user-attachments/assets/855ff4db-2aba-44de-8a6b-543b75bcc174)

3.Creating Internet Gateway and Attaching to VPC

![Screenshot (20)](https://github.com/user-attachments/assets/a9f8679d-d21e-4c75-82dd-c6aead43748d)

![Screenshot (21)](https://github.com/user-attachments/assets/b65468a4-cac3-4987-8241-d4ccf03beaa7)


4.Creating Route Table

![Screenshot (22)](https://github.com/user-attachments/assets/3e45f9eb-49be-4763-8b9b-e38b6820cd55)

![Screenshot (24)](https://github.com/user-attachments/assets/303b23ae-b780-44cf-9d25-4f89e555b1d2)

5.Creating Security Group

![Screenshot (26)](https://github.com/user-attachments/assets/dce74298-29c3-4be2-8891-79e392b1e221)

![Screenshot (44)](https://github.com/user-attachments/assets/8172057f-7b38-45af-95d9-8b91b41612ff)

6.VPC Resource Map

![Screenshot (45)](https://github.com/user-attachments/assets/e28c6259-91b7-4cd7-ad0a-51c129994ff9)

## DELIVERABLES

7.EC2 Instance

![Screenshot (41)](https://github.com/user-attachments/assets/08f6e331-e7af-4023-9057-02ebf1b0ff9d)

![Screenshot (42)](https://github.com/user-attachments/assets/f69f9d19-8d2e-49fb-b75e-6f35d2b7703a)

8.Accessing the Public in Browser

![Screenshot (32)](https://github.com/user-attachments/assets/79873252-3560-4c0f-bb75-4a7222c7515b)

9.From web_server,Trying Private IP of db_server(PING)

![Screenshot (33)](https://github.com/user-attachments/assets/0e8e4aed-c5c9-4785-9ef9-e7a88513d870)




## EXPLANATION

First we need to create a key pair i have not created becase i have already one created and it named as kp, to securely ssh into my ec2 instances, keeping the private key safe. then,i created a vpc named two-tier-vpc to organize my resources. inside it,i set up two subnets: a public subnet with auto-assign public ip enabled and a private subnet without it, both tied to my vpc. to allow internet access,i created an internet gateway and attached it to the vpc. next, i built a public route table, added a route sending all traffic (0.0.0.0/0) to the internet gateway, and linked it to the public subnet. for the private subnet,i created a separate route table with no internet gateway route to keep it isolated.i also made two security groups: one for the public instance, allowing http and ssh from my ip,and another for the private instance, permitting ssh and icmp (ping) from the public subnet’s cidr.in the aws vpc console resource map,i checked that my vpc, subnets, internet gateway, and route tables were properly connected. then, i launched two ec2 instances one public instance web-server in the public subnet with auto-assign public ip enabled, and a private instance db-server in the private subnet without a public ip. for both, i selected my two-tier-vpc, the respective subnets, the kp key pair, and the corresponding security groups. in the public instance’s user data, i added a script to install apache and serve a webpage displaying a welcome message. after launching, i accessed the public instance’s public ip using and my webpage loaded, showing the message i scripted. to test connectivity, i ssh into the public instance with my key pair and tried pinging the private instance’s private ip. it failed at first with a timeout, but if we add an inbound icmp rule to the private instance security group, the ping worked, proving my web-server could reach my db-server. then, i ssh into the private instance via the public instance and tried pinging google, which failed, confirming the private instance has no outbound internet access, as intended public ip.My webpage loaded successfully.












