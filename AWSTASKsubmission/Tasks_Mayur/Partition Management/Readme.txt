Step 1:
//Click Launch Instances On the EC2 dashboard, click Launch Instances.
//Configure Basic Instance Details:
//Name: Enter a name for your instance.
//Select AMI (Amazon Machine Image) as Amazon Linux as the operating system.
//Select an instance type based on your workload.
//Key Pair (SSH):Create or select an existing key pair to securely connect to the instance.
//Security Group: Configure or select existing security group.
//Verify all details and click Launch Instance.

Step 2:
//Go to EC2 resources and click on volume.
//Create a New Volume from EC2 resources which is Volumes.
//Click Create Volume and Select the desired Size, Availability Zone, and Volume Type.
//Click Create Volume.

Step 3:
//Attach that New Volume to Your Instance:
//Select the volume you just created.
//Click Actions > Attach Volume.
//Choose your EC2 instance from the list and attach the volume.

Step 4:
//Get access to your Instance using SSH.
//List the available disks using command lsblk.

#lsblk

//you will see newly added volume.
//Check if that newly added volume is already formatted or not.

#sudo file -s /dev/xvdc

//If it says "data" the volume is unformatted.
//Format the volume using below command.

#sudo mkfs -t ext4 /dev/xvdc

Step 5:
//Now we have to mount that volume.
//Create a mount point.

#sudo mkdir /mnt/newvolume

//mount point is created successfully.
//Now mount the volume to this mount point.

#sudo mount /dev/xvdf /mnt/newvolume

//Now we mounted the volume successfully.
//To verify it use following command.

#df -h

//It will display the volumes.
//We successfully mounted the volume ..!!

//But this mounting is only the temporary mounting.
//When we reboot the system it will automatically get unmounted.
//So if we want mount it permanently then we have to mount it permanently.


