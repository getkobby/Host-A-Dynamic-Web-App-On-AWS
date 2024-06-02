# Host-A-Dynamic-Web-App-On-AWS
Step by Step Guide on Hosting A Dynamic Website on AWS

This AWS architecture describes a well-architected and resilient infrastructure setup for hosting a website, 
leveraging various AWS services for scalability, security, and reliability. 
Here’s a detailed breakdown of each component and its role within the infrastructure:

AWS Resources and Their Roles

1. Virtual Private Cloud (VPC):
   - Description: Provides a logically isolated network for AWS resources.
   - Role: Ensures secure and customizable networking.

2. Internet Gateway:
   - Description: Allows VPC instances to connect to the internet.
   - Role: Facilitates inbound and outbound internet traffic for public subnets.

3. Security Groups:
   - Description: Act as stateful firewalls for controlling traffic to and from instances.
   - Role: Enhance security by specifying allowed inbound and outbound traffic.

4. Availability Zones:
   - Description: Isolated locations within AWS regions.
   - Role: Increase fault tolerance and availability by distributing resources across multiple zones.

5. Public Subnets:
   - Description: Subnets that have a direct route to the internet.
   - Role: Host internet-facing resources such as NAT Gateway and Application Load Balancer.

6. Private Subnets:
   - Description: Subnets without direct access to the internet.
   - Role: Host internal resources like web servers for enhanced security.

7. NAT Gateway:
   - Description: Allows instances in private subnets to access the internet.
   - Role: Enables outgoing internet access for updates and patches while maintaining the security of private instances.

8. EC2 Instance Connect Endpoint:
   - Description: Provides a secure way to connect to EC2 instances.
   - Role: Enables SSH access to instances without requiring public IPs.

9. Application Load Balancer:
   - Description: Distributes incoming traffic across multiple instances.
   - Role: Ensures high availability and scalability by balancing load.

10. Auto Scaling Group:
    - Description: Automatically adjusts the number of EC2 instances based on demand.
    - Role: Ensures application availability and scalability.

11. AWS Certificate Manager:
    - Description: Manages SSL/TLS certificates.
    - Role: Secures application communications by encrypting traffic.

12. **Simple Notification Service (SNS)**:
    - **Description**: Sends notifications for various events.
    - **Role**: Provides alerts about Auto Scaling activities or other significant events.

13. Route 53:
    - Description: AWS’s DNS service.
    - Role: Manages domain names and DNS settings for the website.

14. S3 Bucket:
    - Description: Object storage service.
    - Role: Stores website assets and deployment packages.

Deployment and Usage

Deployment

1. Clone the Repository:
   - Clone the GitHub repository containing the infrastructure code and deployment scripts.

2. Provision AWS Resources:
   - Use the provided scripts to create and configure the necessary AWS resources.
   - This might include CloudFormation templates or Terraform scripts to automate the setup.

3. Deploy Website Code:
   - Upload your website code and assets to the specified S3 bucket.
   - This step ensures your application files are available for deployment.

4. Configure DNS:
   - Set up DNS records in Route 53 to point your domain name to the Application Load Balancer.

Usage

1. Access the Website:
   - Once the deployment is complete and DNS propagation is done,
   - you can access your website using the registered domain name.

Infrastructure Reference Diagram

The reference diagram should visually represent the following key components and their interactions:

- VPC: Central component containing subnets.
- Public Subnets: Show placement of Internet Gateway, NAT Gateway, and Application Load Balancer.
- Private Subnets: Show EC2 instances and their connections to the NAT Gateway.
- Auto Scaling Group: Indicate multiple EC2 instances with an auto-scaling icon.
- Route 53: Show the domain name pointing to the Application Load Balancer.
- S3 Bucket: Represent storage for website assets.
- SNS: Indicate notification flow.
- AWS Certificate Manager: Show secure communication path to the Application Load Balancer.

This architecture ensures high availability, security, and scalability for your web application, 
leveraging multiple AWS services to achieve these goals.
