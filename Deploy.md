# Web Deployment on EC2 Instance

In this guide, we'll walk through the process of deploying a web application on an EC2 instance using Apache HTTP Server (httpd) on a Linux-based system. Below are the commands involved in the deployment process:

### 1. Update Packages

```bash
sudo su -
yum update -y
```

* sudo su -: Switch to the root user to perform administrative tasks.
* yum update -y: Update all installed packages to the latest versions.


###  2. Install Apache HTTP Server

```bash
yum install -y httpd
```

* yum install -y httpd: Install the Apache HTTP Server package.

### 3. Check HTTPD Service Status

```bash
systemctl status httpd
```

This command checks the status of the Apache HTTP Server service to see if it's running.

### 4. Create Directory for Web Content

```bash
mkdir temp
cd temp
```

* mkdir temp: Create a directory named 'temp'.
* cd temp: Change directory to 'temp'.

### 5. Download and Extract Web Application

```bash
wget [awswebdemo](https://awsweb-demo.s3.amazonaws.com/awswebdemo.zip)https://awsweb-demo.s3.amazonaws.com/awswebdemo.zip
```

```bash
unzip awswebdemo.zip
cd awswebdemo
```


* wget <URL>: Download the web application ZIP file.
* unzip awswebdemo.zip: Extract the contents of the ZIP file.
* cd awswebdemo: Change directory to the extracted folder.


### 6. Move Web Content to Document Root

```bash
ls -lrt
mv * /var/www/html
```

* ls -lrt: List files in the current directory.
* mv * /var/www/html: Move all files and directories to the Apache document root directory.


### 7. Enable and Start HTTPD Service

```bash 
systemctl status httpd
systemctl enable httpd
systemctl start httpd
```

* systemctl enable httpd: Enable the Apache HTTP Server service to start automatically on boot.
* systemctl start httpd: Start the Apache HTTP Server service.
* systemctl status httpd: This command is used to check the status of the Apache HTTP Server service (httpd) on a Linux system.


These commands allow you to set up a basic web server environment on your EC2 instance and deploy a web application accessible via the instance's public IP address or domain name.
