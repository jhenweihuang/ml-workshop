# AI&ML Hands-on Workshop
AWS AI and Machine Learning Hands-on Workshop

### Launch EC2 instance using the deep learning AMI

1. Create EC2 IAM role for the workshop as described [here](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/iam-roles-for-amazon-ec2.html#create-iam-role). You can assign admin role for practice. Remember to elete this role after workshop.
    * Role name: mlworkshop
    * Attached policy: AdministratorAccess
2. Launch EC2 Instance using the Deep Learning AMI
    * Region: us-east-1, US East (N. Virginia)
    * AMI: Deep Learning AMI (Ubuntu) Version 8.0 (ami-dff741a0)
    * Instance Type: c4.xlarge ($0.199/hour, http://amzn.to/2j3FdOZ)
3. Connect via SSH and tunnel port 8888:
    * Linux, Mac:
        - `ssh -i user.pem -L 8888:localhost:8888 ubuntu@ec2-ip-ip-ip-ip.region.compute.amazonaws.com`
    * Windows: 
        - Follow the instructions [here](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/putty.html) to download PuTTY and to convert your private key
        - Host Name: `ubuntu@ec2-ip-ip-ip-ip.region.compute.amazonaws.com`
        - Expand Connection and choose Auth, select your .ppk file
        - Expand Connection > SSH, choose Tunnels, specify Source Port: `8888`, Destination: `localhost:8888`
        - Choose Add and Open
4. Clone rekognition-workshop github repository
    * `git clone https://github.com/jhenweihuang/ml-workshop.git`
5. Start jupyter notebook
    * `jupyter notebook`
6. Get the login url with token
    * look for `http://localhost:8888/?token=<your_login_token>`
7. Open notebook 
    * [Amazon Polly Notebook](Notebooks/Polly_Workshop.ipynb)
    * [Amazon Rekognition Notebook](Notebooks/Rekognition_Workshop.ipynb)
8. Follow steps in notebook
9. Delete services after workshop
