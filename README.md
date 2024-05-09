# AWS-Project

**Static Website**
A static website is a collection of web pages that are delivered to the user's web browser exactly as stored. These web pages are written in HTML, CSS, and JavaScript and are pre-designed before being deployed to a web server. Unlike dynamic websites, static websites do not contain server-side processing logic or database interactions. They are suitable for content that does not change frequently, such as company brochures, portfolios, or blogs with infrequent updates.

**EC2**
EC2 stands for Elastic Compute Cloud, which is a web service provided by Amazon Web Services (AWS) that allows users to rent virtual servers called instances. These instances provide scalable compute capacity in the cloud and can be configured with various operating systems, applications, and network configurations. EC2 instances are commonly used for hosting websites, running applications, performing data processing tasks, and more.

**Apache HTTP Server**
HTTPD, or the Apache HTTP Server, is an open-source web server software developed and maintained by the Apache Software Foundation. It is one of the most widely used web server software in the world. HTTPD is capable of serving static and dynamic content over the HTTP protocol and is highly extensible through modules. It supports various features such as virtual hosting, SSL/TLS encryption, URL rewriting, and more. HTTPD is commonly used to host websites and web applications on servers.

Deploying a static website using AWS EC2 Instance 

1.	Login to AWS Console: Go to https://aws.amazon.com/ and login with your credentials.
2.	Navigate to EC2 Dashboard: Once logged in, go to the EC2 Dashboard.
3.	Launch Instance: Click on the "Launch Instance" button to start the process.
4.	Choose AMI: Select the Amazon Machine Image (AMI) that suits your needs. For example, you can choose Amazon Linux or Ubuntu Server.
5.	Select Instance Type: Choose the instance type based on your requirements. For example, a t2.micro instance is suitable for testing.
6.	Configure Instance Details: Set up details like the number of instances, VPC, subnet, etc.
    ## aws ec2 run-instances --image-id ami-12345678 --instance-type t2.micro --count 1 --subnet-id subnet-12345678
7.	Configure Storage: Set the storage size and type.
    ## aws ec2 create-volume --volume-type gp2 --size 8 --availability-zone us-west-2a
8.	Add Tags: Optionally, add tags for better organization.
    ## aws ec2 create-tags --resources i-1234567890abcdef0 --tags Key=Name,Value=MyInstance
9.	Configure Security Group: Create or select a security group to control inbound and outbound traffic.
    ## aws ec2 create-security-group --group-name MySecurityGroup --description "My security group"
10.	Select Key Pair: Choose or create a key pair for SSH access.
    ## aws ec2 create-key-pair --key-name MyKeyPair
11.	Launch Instance: Finally, launch the instance.
    ## aws ec2 run-instances --image-id ami-12345678 --key-name MyKeyPair --security-group-ids sg-903004f8 --instance-type t2.micro --subnet-id subnet-6e7f829e
12.	Connect to Instance: Use SSH to connect to the instance.
    ## ssh -i /path/to/your/keypair.pem ec2-user@your-instance-public-ip
13.	Deploy HTML File: Create and deploy the index.html file on the instance.
14.	Install Apache2: Install and start the Apache2 web server.
    ## sudo yum update -y
    ## sudo yum install httpd -y
    ## sudo systemctl start httpd
    ## sudo systemctl enable httpd
15.	Access the Website: Go to your instance's public IP address in a web browser to view the deployed index.html file.



