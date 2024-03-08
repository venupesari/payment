# Payment Service 
# From Git Bash push

This service is responsible for payments in RoboShop e-commerce app. While creating Ec2 instance please select Devops-Practice AMI From Communicty AMIS.

This service is written on `Python 3.6`, So need it to run this app.

CentOS 7 comes with `Python 3` by default. So we need `Python 3` to be installed.

1. Install Python 3

```
# yum install python36 gcc python3-devel -y
```

2. Create a user for running the application 

```
# useradd roboshop
```

3. Download the repo.

```
$ cd /home/roboshop
$ curl -L -s -o /tmp/payment.zip "https://github.com/rshaik4devops/payment/archive/main.zip"
$ unzip /tmp/payment.zip
$ mv payment-main payment
```

4. Install the dependencies

```
# cd /home/roboshop/payment 
# pip3.6 install -r requirements.txt
```

**Note: Above command may fail with permission denied, So run as root user**

5. Update the roboshop user and group id in `payment.ini` file.

6. Setup the service 

```
# mv /home/roboshop/payment/systemd.service /etc/systemd/system/payment.service
# systemctl daemon-reload
# systemctl enable payment 
# systemctl start payment
```

