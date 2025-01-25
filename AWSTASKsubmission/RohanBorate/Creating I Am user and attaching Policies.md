# Creating I Am user and attaching Policies





- [ ] go to AWS  IAM service  --> IAM ->Users -> create user
![image.png](https://eraser.imgix.net/workspaces/EJ3iJdJH120ujDdkAoyz/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/2GGEPr_zM3tWC0FzF_UtF.png?ixlib=js-3.7.0 "image.png")





![image.png](https://eraser.imgix.net/workspaces/EJ3iJdJH120ujDdkAoyz/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/0Np6Pt-Mq70fjibkHuDqo.png?ixlib=js-3.7.0 "image.png")



![image.png](https://eraser.imgix.net/workspaces/EJ3iJdJH120ujDdkAoyz/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/fBogLCRHvI8_mPFGe0XMW.png?ixlib=js-3.7.0 "image.png")

![image.png](https://eraser.imgix.net/workspaces/EJ3iJdJH120ujDdkAoyz/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/tWT0bWcIbVJmfVFXvwLr8.png?ixlib=js-3.7.0 "image.png")



- [ ] user is created , download the .CSV file which contain user credentials 


![image.png](https://eraser.imgix.net/workspaces/EJ3iJdJH120ujDdkAoyz/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/ZqfiYVACaVnGUiF9b-T08.png?ixlib=js-3.7.0 "image.png")

- [ ] Now login to that  I am user using user credentials 
after entering credentials , that I am user needs to set their custom password



![image.png](https://eraser.imgix.net/workspaces/EJ3iJdJH120ujDdkAoyz/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/mBcvx6XEGeU7m0d-1Wes6.png?ixlib=js-3.7.0 "image.png")

now set that custom password ,

- [ ] we are now logged in with I am user and see , we don't have access to any services 
![image.png](https://eraser.imgix.net/workspaces/EJ3iJdJH120ujDdkAoyz/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/2fPH1BlRR1mhA6qhU93xQ.png?ixlib=js-3.7.0 "image.png")

- [ ] lets try to create an ec2 user , we don't have permission to create ec2 instance , so it gives error


![image.png](https://eraser.imgix.net/workspaces/EJ3iJdJH120ujDdkAoyz/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/A-X_9vcaZakj81bwOzOSb.png?ixlib=js-3.7.0 "image.png")

- [ ] now login to root account and assign policies to Iam user for EC2 instance creation 
basically give permission for EC2 service 

![image.png](https://eraser.imgix.net/workspaces/EJ3iJdJH120ujDdkAoyz/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/0z1385cyDKDyYDhuZKLFd.png?ixlib=js-3.7.0 "image.png")

![image.png](https://eraser.imgix.net/workspaces/EJ3iJdJH120ujDdkAoyz/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/nF1WxnspF3pV9wyHiG2Ff.png?ixlib=js-3.7.0 "image.png")

- [ ] policy is added (you can also create your own custom polices)


![image.png](https://eraser.imgix.net/workspaces/EJ3iJdJH120ujDdkAoyz/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/tvKdnTXlCVaizf-HB4OuD.png?ixlib=js-3.7.0 "image.png")

- [ ] now go I AM user login and check we getting the access for EC2 service 
![image.png](https://eraser.imgix.net/workspaces/EJ3iJdJH120ujDdkAoyz/yuIy5hbLwHZ10ovGIULZ9qCXT8E3/DE0dCxbZXst5cYd0JN_Bs.png?ixlib=js-3.7.0 "image.png")

In this way , AWS  IAM service works .....

