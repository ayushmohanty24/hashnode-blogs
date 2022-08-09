## Creating a Custom VPC and VPC Peering in AWS

Hi Everyone, in the [last article](https://ayush24.hashnode.dev/all-about-aws-vpc) we discussed the different VPC terminologies. That may have given you a high-level idea about a VPC in AWS.

In this article, we are going to create a custom VPC with a public and a private subnet. Each subnet will have an EC2 instance. We will also be Creating a peering Connection Between 2 VPCs.

### Creating a Custom VPC

- Log into your AWS console and select VPC, Click on Your VPCs in the left sidebar and then click on Create VPC.

![create vpc.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658830180371/Ej4-nQXfv.png align="left")

- Give a name to your VPC and the IPv4 CIDR block that you would like. You can enforce the tenancy of EC2 instances launched in this VPC. If you select dedicated then all your instances will be launched on dedicated tenancy instances (more cost). If you select the Default option then instances will use the tenancy option selected while launching them.


![create vpc.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658831518407/UM5qgSIyk.png align="left")
Click on the Create button to create your custom VPC!



![locate vpc.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658831580768/M9evrPPt0Y.png align="left")

Now, you can see your custom VPC along with the default VPC.

- Now let’s create our public and private subnets by selecting the Subnets tab from the left sidebar and clicking on the Create Subnet button.


![public subnet creation.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658837554253/TQTsPSAAI.png align="left")


Let’s first create the public subnet. First, select the recently made VPC. You can give a  name to the subnet to easily identify it, then select an IPv4 CIDR block for this subnet. Here, I am selecting 10.0.1.0/24 as the CIDR block.

You can also select the AZ in which you would like to create this subnet since a subnet always maps to one AZ.

Once done, click on the Create button to create the subnet.

- Now we have to create another subnet which will be the Private Subnet.


![private subnet creation.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658846380214/3KgbMQWdv.png align="left")

- By default, subnets have the Auto-Assign Public IP setting as disabled. Let’s enable this for our public subnet by selecting it and clicking on the Actions dropdown at the top and selecting Edit subnet settings. 
After enabling Auto-Assign Public IP, save it.

![edit private subnet.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658832128816/P_bDfD-rV.png align="left")

- Now we have to create an Internet Gateway.
Without an internet gateway attached, any instance created inside that VPC cannot be accessed via the internet.

To create an internet gateway go to the Internet Gateways tab in the left sidebar and click on Create Internet Gateway at the top. Give a name to your internet gateway and click on the Save button.

![create igw.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658832345709/azhvBXoeF.png align="left")

-  You need to attach the internet gateway with your custom VPC. You can do this by selecting it, clicking on the Actions dropdown at the top and selecting Attach to VPC.


![attach vpc.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658832476129/bemal77IV.png align="left")

Then select your custom VPC and click on the Attach button.


![attach igw.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658832499121/sbfG11-K6.png align="left")

- Now we have to create a Route Table

For security reasons, it is recommended to leave the main route table as it is. Hence, we will be creating a new route table for our custom VPC and allow internet access to our public subnet through it.

Let’s head to the Route Tables tab from the left sidebar and click on the Create route table button at the top.

Give a name to your route table, select the custom VPC and click on the Create Route Table.


![rote create.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658832641304/FvD2Zjdab.png align="left")

- Let's associate the public subnet with the custom route table by selecting it and navigating to the Subnet Associations tab at the bottom.

Click on the Edit subnet associations and select the public subnet and click on the Save button.
![edit rt.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658832938663/6c_zi3JNj.png align="left")


![associate public to rt.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658838565236/dnvK9S_hZ.png align="left")

- Now create another route table for the private subnet.

![private route.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658834192475/jFNiwisaU.png align="left")

![edit private route.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658834208659/JsAtt4CZT.png align="left")

- Now to allow internet access to our public subnet we need to create a new Route for our custom route table.

Select the custom route table and navigate to the Routes tab at the bottom. Click on the Edit Routes button and add a new Route with the destination as 0.0.0.0/0 i.e. the Internet and Target as the attached internet gateway.


![igw to route.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658833105432/t-CYXxCND.png align="left")

Save the Routes and now your public subnet has internet access.

- Now we have to create a NAT gateway. 

Select the NAT gateways from the side menu bar and click on Create NAT gateway.

![create NAT.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658833565150/AT4rYSAFk.png align="left")

Give a name to your NAT gateway, select the custom public subnet and assign the elastic IP. Click on the create button.

![nat settings.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658833647914/Tw4OscqXw.png align="left")

- Now we have to move to the Route Table and select the custom-made Private route table and click on the Edit button.

![edit private route.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658834464668/dZJHNTE4i.png align="left")

Add the custom-made NAT IP to the private route.


![nat to private route.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658834613770/z9P5WVyz-.png align="left")

- It’s time to launch our instances. Head over to the EC2 dashboard and click on Launch Instance.
Select the custom VPC as the network and the public subnet as the subnet. Now, in the field just below the subnet, you can see the field Auto-assign Public IP and its value is set to the subnet setting.

Since in our subnet, we enabled this option so the default option here is Enable.


![instance setting.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658835014853/ynPLrZIcM.png align="left")


![Screenshot 2022-07-26 165659.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658835026717/KRAo0jyr-.png align="left")

- Now, to create a private instance, select the same AMI and instance type. Just this time select the private subnet to launch the instance.

![private instace.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658835255973/3sHQxq0au.png align="left")

### SSH into Instances
It’s time to SSH into your instances but since your private instance does not have a public IP address you won’t be able to SSH into it directly from your system.

So let's first SSH into the public instance.

![connection public.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658840439104/P_rMi3RRx.png align="left")

Now, that we are inside the public subnet we should be able to SSH into our private subnet since by default instances within a VPC can communicate with each other.

To SSH, we need the private key, so create a .pem file and copy the contents of your downloaded PEM file in it. You can do create a new file by typing the following commands

- ```vi private.pem``` to open VIM

- Press ```i``` to enter insert mode of VIM

- Copy the content of your downloaded PEM file and paste in the terminal.

- Press Escape key to exit the insert mode and type ```:wq``` to save the file and quit

- Now, type ```chmod 600 private.pem``` to limit permissions of the file

![private connection.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658840710186/yevGVQtCy.png align="left")

### With this, you have successfully created a custom VPC.

# VPC Peering

A VPC peering connection is a networking connection between two VPCs that enables you to route traffic between them using private IPv4 addresses or IPv6 addresses. Instances in either VPC can communicate with each other as if they are within the same network.

#### Here we have to create 2 VPCs to connect them with each other.
- Previously we had created One Vpc. 
- Using the same steps we have to Create another VPC. 
- We can create the VPC in any region but here we will be creating the VPC in the same region as the first VPC
- The CIDR range should be always different from that of the First VPC.

#### After creating another VPC successfully.

- Select the peering connections from the side menu bar. Click on the Create Peering connection.

![peering connection.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658844691808/H0n-A9NaM.png align="left")

- Give a name to the Connection, Select the requester as one VPC and the Accepter as another VPC. Select "Create Peering Connection".
- Go back to the Peering Connection page, Select the created connection go to actions, and select "Accept Request"

![accept request peering.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658845016024/LbFQ9w-HO.png align="left")

- Now we have to Modify our Route tables.

Select the "Route Tables" from the side menu bar. Select the public Route table which we made for our first VPC, and Edit Route to add the newly created VPC's CIDR range.


![public route peering.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658845494963/W0iFcTAo5.png align="left")

Similarly, Edit the private route table.


![private route peering.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658845639512/wpr_rVhKj.png align="left")

- Now, select the Route table which was created for the Second VPC, and edit it to add the First VPC's CIDR range.

![2nd vpc route peering.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658845799241/DNUs-odeL.png align="left")

#### To check whether the Peering is correctly performed.

Go to the shell and connect the Instance linked to the Second VPC. Try connecting to the First VPC through the second VPC by typing ````ping "First VPC's CIDR"````


![check peering.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658846166481/NWkbF36H3.png align="left")











