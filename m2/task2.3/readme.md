## Task 2.3
### Module 2. Virtualization and Cloud Basic
:white_check_mark: **1. Read the terms of Using the AWS Free Tier and the ability to control their own costs.**  
https://docs.aws.amazon.com/en_us/awsaccountbilling/latest/aboutv2/billing-free-tier.html  

:white_check_mark: **2. Review the 10-minute example Launch a Linux Virtual Machine.**  
Repeat, create my own VM in the AWS cloud and connect to it (use `t2.micro` and _CentOS_).  
https://aws.amazon.com/getting-started/tutorials/launch-a-virtual-machine/?trk=gs_card  
2.1. Create Lightsail account.  
2.2. Create Lightsail instance.  
2.3.a. Instance location - **Frankfurt, Zone A (eu-central-1a)**  
2.3.b. Linux/Unix, OS only.  
2.3.c. OS - CentOS.  
2.3.g. Plan - 3,50 USD (512MB RAM, 1 vCPU, 20GB SSD, transfer 1TB), first month free.  
2.3.h. Instance name - `centos-1`   
2.3.i. Add key-only tag - `maxim`  
2.3.j. Creating.  
![Sshot 1](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.3/shots/1_create_light_inst.png "Sshot 1")  
2.4. Connect to the instance.  
2.4.a. Instances - SSH through WEB browser:
![Sshot 2](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.3/shots/2_lightsail_ssh.png "Sshot 2")  
2.5. Stop the instance.  

:white_check_mark: **3. Review the 10-minute example Store and Retrieve a File. Repeat, create my own repository.**  
https://aws.amazon.com/getting-started/tutorials/backup-files-to-amazon-s3/?trk=gs_card  
3.1. AWS console S3 service login.  
3.2. Create S3 bucket.  
3.2.a. Create bucket.  
3.2.b. Bucket name - `max-bckt`, region - **US East (Ohio)**.  
3.2.c. No additional options.  
3.2.d. Leave default permissions (`Block all public access`).  
![Sshot 3](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.3/shots/3_create_bucket.png "Sshot 3")  
3.2.e. Check and create.  
![Sshot 4](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.3/shots/4_manage_buckets.png "Sshot 4")  
3.3. Send a file.  
3.3.a. Open a bucket.  
3.3.b. Press the "Upload" button.  
3.3.c. Select and add the files (my screenshots).  
3.3.d. Leave default permissions.  
3.3.e. Leave default privileges.  
![Sshot 5](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.3/shots/5_upload_files.png "Sshot 5")  
3.3.f. Check and send.  
![Sshot 6](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.3/shots/6_files_list.png "Sshot 6")  
3.4. Extract an object.  
3.4.a. Mark a file and press the "Download" button.  
3.5. Remove an object and a bucket.  
3.5.a. Mark a file, select the "Actions-Delete" menu.  
3.5.b. Check and confirm delete.  
3.5.c. Go to the Amazon S3 to view all buckets.  
3.5.d. Mark a bucket and press the "Delete" button, type its name to confirm.  

:black_square_button: **4. Review the 10-minute example. Repeat the steps, create my own site.**  
https://aws.amazon.com/ru/getting-started/tutorials/launch-a-wordpress-website/  
4.1. Create an Amazon Lightsail Account.  
4.2. Create a WordPress instance in Lightsail.  
4.2.a. Sign into the Lightsail console.  
4.2.b. On the Instances tab of the Lightsail home page, choose Create instance.  
4.2.c. Choose the AWS Region and Availability Zone for your instance - **Frankfurt, Zone A (eu-central-1a)**.  
4.2.d. Choose instance image Linux/Unix, WordPress. 
4.2.e. Choose an instance plan 3,50 USD (512MB RAM, 1 vCPU, 20GB SSD, transfer 1TB), first month free.   
4.2.f. Enter a name for instance - **`wp-max`**  
4.2.g. Choose Create instance.  
![Sshot 7](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.3/shots/7_wordpress_lightsail.png "Sshot 7")  

:black_square_button: **5. Review the 10-minute example. Create my own domain and domain name for my site.**  
https://aws.amazon.com/getting-started/hands-on/get-a-domain/?nc1=h_ls  

:black_square_button: **6. Review the example. Create a user AWS IAM, configure CLI AWS and upload files to S3.**  
https://aws.amazon.com/getting-started/hands-on/backup-to-s3-cli/?nc1=h_ls  

:black_square_button: **7. Create a static site in S3, publicly available.** Post on the page my own photo,  
the name of the educational program and a list of AWS services with which I worked.  


