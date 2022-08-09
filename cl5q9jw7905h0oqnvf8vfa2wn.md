## How to Attach and Mount an EBS volume to EC2  Instance

# Mount an EBS volume to EC2 Instance

##### Follow the steps given below carefully for the setup.

Step 1: Launch an EC2 Instance


![Screenshot 2022-07-16 111733.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657950479045/kn5VNfRGd.png align="left")

Step 2: Create a new Volume, Confirm the Availability Zone from the Instance Created and select the same in the new Volume.


![Screenshot 2022-07-16 111627.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657950434962/jAC8tYBvE.png align="left")


![Screenshot 2022-07-16 111905.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657950635039/Ndtiusjkl.png align="left")

Step 3: Select the created volume, Click on Actions and select the “attach volume” option.


![Screenshot 2022-07-16 112320.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657950840718/kbAOy1LFg.png align="left")

Step 4: Select the ec2 instance from the instance text box and Select Attach Volume.


![Screenshot 2022-07-16 112601.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657950982666/o3mbYg5Qy.png align="left")

Step 5: Connect your EC2 instance 

![Screenshot 2022-07-16 115650.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657952836530/97ROaxiDh.png align="left")

Step 6: Use the following command to shift to the root user.

`Sudo su`

`cd`


![Screenshot 2022-07-16 120545.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657953391356/h_2EOT6zk.png align="left")

Step 7: List the available disks using the following command, here you can also find the disk you attached to your instance.

`lsblk`


![Screenshot 2022-07-16 120608.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657953399637/NdQZ9SAOs.png align="left")

Step 8: Format the volume to the ext4 filesystem using the following command.

`mkfs.ext4 /dev/xvdf`


![Screenshot 2022-07-16 121126.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657953717222/ZWUuNtQz_.png align="left")

Step 9: Create a directory of your choice to mount the new volume. 

`mkdir /new-volume`

`cd /`

`cd new-volume/`


![Screenshot 2022-07-16 122836.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657954744422/ecV7jg4CH.png align="left")

Step 10: Mount the volume to the “new-volume” directory using the following command and check the disk space to validate the volume mount.

`mount /dev/xvdf /new-volume/`

`df -h`


![Screenshot 2022-07-16 123427.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657955131226/uUCMtHthW.png align="left")
##### Volume is now successfully mounted to the EC2 Instance.


# Automount EBS Volume on Reboot

By default on every reboot, the EBS volumes other than root volume will get unmounted.
 
To enable automount, Follow the steps given below to automount the EBS volume to ec2 instance.

Step 1: Open the "fstab" file

`vi /etc/fstab`

Step 2: Make an entry in the following format.

`/dev/xvdf       /new-volume   ext4    defaults,noatime        1       1`


![Screenshot 2022-07-16 131423.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657957504734/DLVXQutmG.png align="left")

Step 3: Execute the following command to check if the "fstab" file has any error, If the command shows no error, it means the "fstab" entry is good.

`mount -a`


![Screenshot 2022-07-16 131813.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657957715755/pKpgCBpYF.png align="left")

##### Now, on every reboot, the extra EBS volumes will get mounted automatically.

# How To increase the size of the volume?

Step 1: Visit the volumes section, Select the required volume and click on "Actions" and select "Modify Volume" . Increase the size and click on "Modify".


![Screenshot 2022-07-16 132838.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657958470913/0i7Iayaux.png align="left")


![Screenshot 2022-07-16 132921.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657958520174/lvqm5iLbW.png align="left")

Step 2: Go back to the console, and enter the following command to resize the volume.

`resize2fs /dev/xvdf`

![Screenshot 2022-07-16 133432.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657958695192/RzvaHMhVZ.png align="left")

Step 3: To check, if the volume is successfully increased. Enter the following command.

`df -h`


![Screenshot 2022-07-16 135521.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657959954512/w4xLNFlJx.png align="left")
