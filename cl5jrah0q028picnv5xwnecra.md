## Aws Ec2 Instance

# What is Amazon EC2 Instance?
- An Amazon EC2 instance is a virtual server in Amazon’s Elastic Compute Cloud (EC2) for running applications on the Amazon Web Services (AWS) infrastructure.
- EC2 is a service that enables business subscribers to run application programs in the computing environment.
- *In short*, you can create a server on AWS and deploy your application on that server.
- Amazon provides various types of instances with different configurations of CPU, memory, storage, and networking resources to suit user needs.

# Features of Amazon EC2 Instance

- **Reliable** − Amazon EC2 offers a highly reliable environment where replacement of instances is rapidly possible. Service Level Agreement commitment is 99.9% availability for each Amazon EC2 region.

- **Designed for Amazon Web Services** − Amazon EC2 works fine with Amazon services like Amazon S3, Amazon RDS, Amazon DynamoDB, and Amazon SQS. It provides a complete solution for computing, query processing, and storage across a wide range of applications.

- **Secure** − Amazon EC2 works in Amazon Virtual Private Cloud to provide a secure and robust network of resources.

- **Flexible Tools** − Amazon EC2 provides the tools for developers and system administrators to build failure applications and isolate themselves from common failure situations.

- **Inexpensive** − Amazon EC2 wants us to pay only for the resources that we use. It includes multiple purchase plans such as On-Demand Instances, Reserved Instances, Spot Instances, etc. which we can choose as per our requirement.

# EC2 Instance Types

#### General Purpose EC2 Instance
- This type of instance is the most commonly utilized for testing. There are two types of general-purpose instances: “T” and “M.”
- “T” instances are targeted to simple jobs just like testing environments, and they have modest networking on the most basic options.
- “M” Instances are for general use when you don’t want a testing environment, but want an all-purpose instance. They offer more balanced resources compared to the “T” instance

#### Compute Optimized
- If your application requires the process of a lot of information like math operations, load balancing, rendering tasks, or sometimes video encoding
- You need an instance that can process all that information in less time

#### Memory Optimized
- If your app doesn’t require too much CPU, but instead, needs more and faster RAM; you should check out the available option on the “X1e, X1, and R” instances.

#### Accelerated Computing
- Creating a movie and need to render the textures? Need to design with power? Or do you just have money to spend and want to play games on streaming?
- The Accelerated Computing Instances are best for graphics applications and streaming.

#### Storage Optimized
- These Kind of instances are provisioned with a more significant amount of TB for storage
- You are going to have the best I/O Performance. These instances are a great option for those databases that need to be written regularly on the disk, here we have three groups of instances: H, I, and D.

# How to launch an on-demand AWS EC2 instance in AWS Cloud 

- Sign in to the AWS Management Console.
- Click on the EC2 service.
![Screenshot 2022-07-13 191758.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657720243337/30SuWDD-F.png align="left")
- Click on the Launch Instance button to create a new instance.

![Screenshot 2022-07-13 192147.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657720357051/9QLDbaQcey.png align="left")

- Choose AMI: (Amazon Machine Image) AMI is a template used to create the EC2 instance.

![Screenshot 2022-07-13 192501.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657720524834/M5HJXZfFl.png align="left")

- Choose Instance Type. Suppose I choose a t2.micro as an instance type for testing purpose
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657720839946/bLDdgVgRm.png align="left")

- Create a new KeyPair.
![Screenshot 2022-07-13 193404.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657721155026/vRP_U7c74.png align="left")

![Screenshot 2022-07-13 193431.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657721236523/kmwSa70j8.png align="left")

- In Networks Settings, Leave fields as it is, except Type and Source Type.
Select Type as **ALL TRAFFIC** and Source Type as **ANYWHERE** [It is not recommended to select Anywhere, You can customize it according to your need].

![Screenshot 2022-07-13 195004.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657722290887/HPYwd142V.png align="left")
![Screenshot 2022-07-13 195037.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657722296951/UYtdHZPRk.png align="left")

- Never leave the default 8Gb, if you want to be on the free tier limits you can set a value around 20Gb -24Gb because sometimes you leave it as default and your instance is not going to have too many spaces to do many things


![Screenshot 2022-07-13 195639.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657722470774/fAdMx1RYE.png align="left")
![Screenshot 2022-07-13 195858.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657722560079/eA1blPKZc.png align="left")

- At last, Click on Launch Instance

![Screenshot 2022-07-13 200139.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657722787445/YHlrpRe4G.png align="left")

- Your Instance will be Located here, Add a name for the instance.

![Screenshot 2022-07-13 200354.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657722918175/za058Sp5a.png align="left")
