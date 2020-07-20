## Task 2.4
### Module 2. Virtualization and Cloud Basic

:white_check_mark: **1. Review the 10-minute example Deploy Docker Containers on Amazon Elastic
Container Service (Amazon ECS).**  Repeat, create a cluster, and run the online demo application.  
https://aws.amazon.com/getting-started/hands-on/deploy-docker-containers/?nc1=h_ls  
https://www.youtube.com/watch?v=blChPj05Los&list=PLg5SS_4L6LYsxrZ_4xE_U95AtGsIB96k9&index=74  

**1.** Set up my first run with Amazon ECS - **Europe (Frankfurt) eu-central-1**.  
1.a. Open the Amazon ECS console first run wizard.  
1.b. With Amazon ECS, I do not have Amazon ECR options, I skip to step 2.  

**2.** Create a task definition. _Pay attention_. It is impossible to create EC2 based cluster using this guide,  
because whatever you do - it uses only FARGATE compatible scheme:  
https://console.aws.amazon.com/ecs/home#/firstRun  
So get Started with Amazon Elastic Container Service (Amazon ECS) using **Fargate**.  
![Sshot 01](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.4/pictures/01_get_start_fargate.png "Sshot 01")  

**3.** Configure my service.  
![Sshot 02](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.4/pictures/02_setting_service.png "Sshot 02")  

**4.** Configure my cluster.  
![Sshot 03](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.4/pictures/03_conf_cluster.png "Sshot 03")  

Review settings.  
![Sshot 04](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.4/pictures/04_review_settings.png "Sshot 04")  

**5.** Launch and view created resources.  
![Sshot 05](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.4/pictures/05_creating_completed.png "Sshot 05")  

View service:  
![Sshot 06](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.4/pictures/06_cluster_service_view.png "Sshot 06")  

**6.** Open the Sample Application, check the public IP:  
![Sshot 07](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.4/pictures/07_public_ip.png "Sshot 07")  

Open the public IP in web-browser:  
![Sshot 08](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.4/pictures/08_sample_app_ip.png "Sshot 08")  

Go to the CloudWatch logs:  
![Sshot 09](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.4/pictures/09_cloud_watch.png "Sshot 09")  

**7.** Delete created Resources.  


:negative_squared_cross_mark: 2. *(optional)* To change custom settings and run other application.  

  

