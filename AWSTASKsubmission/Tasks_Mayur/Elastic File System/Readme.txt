//Steps to create Elastic System File.

Step 1:
//Go to the AWS Management Console.
//Open the Elastic File System Service (EFS).

Step 2:
//Click Create file system.
//Give name to the File System.
//Choose the default Virtual Private Cloud (VPC).
//Click on Create.

Step 3:
//Click Launch Instances On the EC2 dashboard, click Launch Instances.
//Configure Basic Instance Details:
//Name: Enter a name for your instance.
//Select AMI (Amazon Machine Image) as Amazon Linux as the operating system.
//Select an instance type based on your workload.
//Key Pair (SSH):Create or select an existing key pair to securely connect to the instance.
//Security Group: Configure or select existing security group.
//Verify all details and click Launch Instance.
//Create a Directory for Mounting on your instance.

#sudo mkdir /mnt/efs

Step 4:
//To Mount the EFS File System find the EFS File System ID.
//In the AWS Management Console, go to EFS.
//Locate the File System ID for your EFS and click on attach.
//Select mount via DNS and copy command mount using the NFS client.

#sudo mount -t nfs4 -o nfsvers=4.1,rsize=1048576,wsize=1048576,hard,timeo=600,retrans=2,noresvport fs-0b6831f57dd6a9b6e.efs.ap-south-1.amazonaws.com:/ efs

//Now paste this command in /mnt/efs directory and hit enter.

Step 6: 
//Test the EFS File System
//Create a Test File in /mnt/efs.

#sudo touch /mnt/efs/mayur1.txt

//List files in the directory.

#ls -l /mnt/efs

//If your test file is listed Reboot your EC2 instance and verify the file still exists in /mnt/efs.
//If you see mayur1.txt file.

//Your EFS is mounted..!!

