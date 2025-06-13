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
First creating a key pair named KP to securely access my EC2 instance via SSH,making sure to save the private key safely. Then,i set up a custom VPC to keep my resources organized and isolated. Inside the VPC,i created a public subnet, configuring it to automatically assign public IPs to any instances i launch there. Next,i built an internet gateway and attached it to my VPC,enabling internet connectivity. To route traffic,i crafted a public route table, added a route directing all outbound traffic (0.0.0.0/0) to the internet gateway,and linked it to my public subnet.After that,i created  a security group to control access, allowing HTTP traffic on port 80 for web access and SSH on port 22 for secure connections.In the AWS VPC console,i checked the resource map to confirm that my VPC,subnet,internet gateway,and route table were all connected perfectly.Then,i launched an EC2 instance in my public subnet,selecting my KP key pair,the public subnet,and the security group i created.i enabled auto-assign public IP and added a user data script to install Apache and serve a custom webpage with a welcome message. Once the instance was running,i used public IP and opened site in my browser—using http since i dont have acces to https port.My webpage loaded successfully.

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

![Screenshot (33)](https://github.com/user-attachments/assets/b6d4da78-d292-4812-aa10-b496dac485bb)

![Screenshot (39)](https://github.com/user-attachments/assets/009e5969-293f-4257-828c-37562cb682f2)



## EXPLANATION














