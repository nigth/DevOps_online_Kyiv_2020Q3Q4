## Task 2.3
### Module 2. Virtualization and Cloud Basic
:white_check_mark: **1. Read the terms of Using the AWS Free Tier and the ability to control their own costs.**  
https://docs.aws.amazon.com/en_us/awsaccountbilling/latest/aboutv2/billing-free-tier.html  

:white_check_mark: **2. Review the 10-minute example Launch a Linux Virtual Machine.**  
Repeat, create my own VM in the AWS cloud and connect to it (use `t2.micro` and _CentOS_).  
https://aws.amazon.com/getting-started/tutorials/launch-a-virtual-machine/?trk=gs_card  
**2.1.** Create Lightsail account.  
**2.2.** Create Lightsail instance.  
**2.3.** Configure my Amazon Lightsail instance.  
2.3.a. Instance location - **Frankfurt, Zone A (eu-central-1a)**  
2.3.b. Linux/Unix, OS only.  
2.3.c. OS - CentOS.  
2.3.g. Plan - 3,50 USD (512MB RAM, 1 vCPU, 20GB SSD, transfer 1TB), first month free.  
2.3.h. Instance name - `centos-1`   
2.3.i. Add key-only tag - `maxim`  
2.3.j. Creating.  
![Sshot 01](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.3/shots/01_create_light_inst.png "Sshot 01")  

**2.4.** Connect to the instance.  
2.4.a. Instances - SSH through WEB browser:
![Sshot 02](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.3/shots/02_lightsail_ssh.png "Sshot 02")  

**2.5.** Stop the instance.  

:white_check_mark: **3. Review the 10-minute example Store and Retrieve a File. Repeat, create my own repository.**  
https://aws.amazon.com/getting-started/tutorials/backup-files-to-amazon-s3/?trk=gs_card  
**3.1.** AWS console S3 service login.  
**3.2.** Create S3 bucket.  
3.2.a. Create bucket.  
3.2.b. Bucket name - `max-bckt`, region - **US East (Ohio)**.  
3.2.c. No additional options.  
3.2.d. Leave default permissions (`Block all public access`).  
![Sshot 03](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.3/shots/03_create_bucket.png "Sshot 03")  

3.2.e. Check and create.  
![Sshot 04](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.3/shots/04_manage_buckets.png "Sshot 04")  

**3.3.** Send a file.  
3.3.a. Open a bucket.  
3.3.b. Press the "Upload" button.  
3.3.c. Select and add the files (my screenshots).  
3.3.d. Leave default permissions.  
3.3.e. Leave default privileges.  
![Sshot 05](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.3/shots/05_upload_files.png "Sshot 05")  

3.3.f. Check and send.  
![Sshot 06](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.3/shots/06_files_list.png "Sshot 06")  

**3.4.** Extract an object.  
3.4.a. Mark a file and press the "Download" button.  
**3.5.** Remove an object and a bucket.  
3.5.a. Mark a file, select the "Actions-Delete" menu.  
3.5.b. Check and confirm delete.  
3.5.c. Go to the Amazon S3 to view all buckets.  
3.5.d. Mark a bucket and press the "Delete" button, type its name to confirm.  

:white_check_mark: **4. Review the 10-minute example. Repeat the steps, create my own site.**  
https://aws.amazon.com/ru/getting-started/tutorials/launch-a-wordpress-website/  
**4.1.** Create an Amazon Lightsail Account.  
**4.2.** Create a WordPress instance in Lightsail.  
4.2.a. Sign into the Lightsail console.  
4.2.b. On the Instances tab of the Lightsail home page, choose Create instance.  
4.2.c. Choose the AWS Region and Av Zone for your instance - **Frankfurt, Zone A (eu-central-1a)**.  
4.2.d. Choose instance image Linux/Unix, WordPress.  
4.2.e. Choose a plan 3,50 USD (512MB RAM, 1 vCPU, 20GB SSD, transfer 1TB), first month free.   
4.2.f. Enter a name for instance - **`wp-max`**  
4.2.g. Choose Create instance.  
![Sshot 07](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.3/shots/07_wordpress_lightsail.png "Sshot 07")  

**4.3.** Connect to WP instance via SSH and get the password for WordPress website.  
4.3.a.Choose the SSH quick-connect icon for my WordPress instance.  
4.3.b. `cat $HOME/bitnami_application_password`  
4.3.c. Make note of the password displayed on the screen.  
**4.4. Sign in to the administration dashboard of my WordPress website**  
4.4.a. `http://My-WP-IpAddress/wp-login.php`  
4.4.b. Log into my instance.  
![Sshot 08](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.3/shots/08_wp_dashboard.png "Sshot 08")  

**4.5.** Create a Lightsail static IP address and attach it to my WordPress instance.  
4.5.a. On the Instances tab of the Lightsail home page, choose my running WordPress instance.  
4.5.b. Choose the Networking tab, then choose Create static IP.  
4.5.c. Select location - **Frankfurt, all zones (eu-central-1)**, attach to the WP instance. 
![Sshot 09](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.3/shots/09_wp_stat_ip.png "Sshot 09")  

4.5.d. Name my static IP `wp-statip`, then choose Create.  
![Sshot 10](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.3/shots/10_wp_get_statip.png "Sshot 10")  

**4.6.** Create a Lightsail DNS zone and map a domain to your WordPress instance.  
4.6.a. On the Networking tab of the Lightsail home page, choose Create DNS zone.  
4.6.b. Enter my domain, then choose Create DNS zone.  
 _*You will need to configure your domain provider to use [Lightsail name servers](https://lightsail.aws.amazon.com/ls/docs/en_us/articles/lightsail-how-to-create-dns-entry)_  
4.6.с. Make note of the name server address listed on the page.  
![Sshot 11](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.3/shots/11_dns_zone_created.png "Sshot 11")  

4.6.d. Add an A record to point the apex of your domain to your WordPress instance, as follows:  
4.6.d.1. In the DNS zone for your domain, choose Add record.  
4.6.d.2. In the Subdomain box, enter an @ symbol to map the apex of my domain to my instance.  
4.6.d.3. In the Maps to box, choose the static IP that is attached to the WordPress instance.  
4.6.d.4. Choose the save icon.  
![Sshot 12](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.3/shots/12_add_a_record.png "Sshot 12")  

**4.7.** Modify main page and create my own site:  
![Sshot 13](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.3/shots/13_my_wp_site.png "Sshot 13")  

**http://myv.pp.ua/**  

You are welcome!  

:white_check_mark: **5. Review the 10-minute example.**
Explore the possibilities of creating my own domain and domain name for my site.  
https://aws.amazon.com/getting-started/hands-on/get-a-domain/?nc1=h_ls  
In the process of exploring the possibilities of creating my domain name for own site,
I decided to use my existing domain name, registered in other registrant, different from AWS.
On the previous sub-task 2.3.4, I transfered DNS-record for it and attached it to the WordPress blog.

:white_check_mark: **6. Review the example. Create a user AWS IAM, configure CLI AWS and upload files to S3.**  
https://aws.amazon.com/getting-started/hands-on/backup-to-s3-cli/?nc1=h_ls  
**6.1.** Create an AWS IAM User.  
6.1.a. Select IAM to open the Identity and Access Management dashboard.  
6.1.b. From the AWS Identity and Access Management dashboard, click on Users on the left side.  
6.1.c. Click the Add user button.  
6.1.d. Enter a user name in the textbox next to _User name_ and select _Programmatic access_.  
6.1.e. Click on Attach existing policies directly option. Select _AdministratorAccess_.  
6.1.f. Review and click on Create user.  
6.1.g. Click the Download button and save the credentials.csv file.  
![Sshot 14](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.3/shots/14_user_created.png "Sshot 14")  

**6.2.** Install and Configure the AWS CLI.  
6.2.a. Follow the directions for installing the AWS CLI bundled installer.  
6.2.b. Open a terminal window.  
6.2.c. Region - **eu-central-1**  
`aws configure`  
![Sshot 15](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.3/shots/15_aws_conf.png "Sshot 15")  

**6.3.** Using the AWS CLI with Amazon S3.  
6.3.a. Create a new bucket:  
`aws s3 mb s3://maxim-backup-bucket`  
6.3.b. Upload the file located in the local directory:  
`aws s3 cp ~/temp/mbackup.bak s3://maxim-backup-bucket/`  
6.3.c. Download file from S3 to the local directory:  
`aws s3 cp s3://maxim-backup-bucket/mbackup.bak ./`  
6.3.d. Delete file from bucket:  
`aws s3 rm s3://maxim-backup-bucket/mbackup.bak`  
![Sshot 16](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.3/shots/16_s3_backup.png "Sshot 16")  

:white_check_mark: **7. Create a static site in S3, publicly available.** Post on the page my own photo,  
the name of the educational program and a list of AWS services with which I worked.  
[Website Endpoints](https://docs.aws.amazon.com/AmazonS3/latest/dev/WebsiteEndpoints.html)  
[Hosting a static website on Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/WebsiteHosting.html)  
[How do I configure an S3 bucket for static website hosting](https://docs.aws.amazon.com/AmazonS3/latest/user-guide/static-website-hosting.html)  
[How to Host a Website on S3 Without Getting Lost in the Sea](https://medium.com/@kyle.galbraith/how-to-host-a-website-on-s3-without-getting-lost-in-the-sea-e2b82aa6cd38)  
7.1. Create a bucket with the same as site name. Region **EU (Frankfurt)**.  
7.2. Uncheck the "Block all public access" option, set Allow all.  
![Sshot 17](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.3/shots/17_create_site_bucket.png "Sshot 17")  

7.3. In the Bucket name list - Choose Properties - Choose Static website hosting.  
![Sshot 18](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.3/shots/18_enable_stat_hosting.png "Sshot 18")  

7.4. Upload site content to the bucket.  
![Sshot 19](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.3/shots/19_uploaded_content.png "Sshot 19")  

7.5. Editing block public access settings for files and folders.  
7.6. Adding a bucket policy to Allow the PublicReadGetObject.  
![Sshot 20](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.3/shots/20_bucket_policy.png "Sshot 20")  

7.7. Test my website endpoint with Amazon provided URL:  
![Sshot 21](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.3/shots/21_endpoint_works.png "Sshot 21")  

**http://www.myv.pp.ua.s3-website.eu-central-1.amazonaws.com/**  

You are welcome!  










