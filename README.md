# django-todo
A simple todo app built with django
![image](https://github.com/KETAKISANTOSHNIKURE/my-docker-repo/assets/133886525/566f65c2-b1d1-43dc-9c0c-4eca52c8a502)

https://github.com/KETAKISANTOSHNIKURE/my-docker-repo/blob/f04a17454d561332edf2fef8076eb14762385f3f/staticfiles/Ketaki_todo.png

![todo App](https://raw.githubusercontent.com/shreys7/django-todo/develop/staticfiles/todoApp.png)

![Ketaki_todo_App]https://raw.github.com/KETAKISANTOSHNIKURE/my-docker-repo/blob/develop/staticfiles/Ketaki_todo.png


### Setup
To get this repository, run the following command inside your git enabled terminal
```bash
$ git clone https://github.com/shreys7/django-todo.git
```
You will need django to be installed in your computer to run this app. Head over to https://www.djangoproject.com/download/ for the download guide

Once you have downloaded django, go to the cloned repo directory and run the following command

```bash
$ python manage.py makemigrations
```

This will create all the migrations file (database migrations) required to run this App.

Now, to apply this migrations run the following command
```bash
$ python manage.py migrate
```

One last step and then our todo App will be live. We need to create an admin user to run this App. On the terminal, type the following command and provide username, password and email for the admin user
```bash
$ python manage.py createsuperuser
```

That was pretty simple, right? Now let's make the App live. We just need to start the server now and then we can start using our simple todo App. Start the server by following command

```bash
$ python manage.py runserver
```

### Docker 
`vi Dockerfile`
`sudo docker build . -t todo-
app`
`docker run -p 8000:8000 c34978796766`
#runs in the background
`docker run -d -p 8000:8000 c34978796766`
### Jenkins
Step 1: Launching an Amazon Linux EC2 instance
[Refer video “How to launch an Amazon Linux ec2 Instance”]

Step 2: Installation of Jenkins on EC2 Instance
i. Run the command to update all the packages.

sudo yum update

ii. Check if java is installed or not using the command

`java -version`

If java is not installed, install using the following command

`sudo dnf install java-11-amazon-corretto -y`

iii. Now, to download the latest Jenkins package

`sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat/jenkins.repo`

**iv. **To enable the installation of the package, import the key file from Jenkins-CI:

`sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key`

(https://raw.githubusercontent.com/shreys7/django-todo/develop/staticfiles/Ketaki_jenkins.png)

v. Install Jenkins on the EC2 instance

`sudo yum install jenkins`

vi. To start the Jenkins service

`sudo service jenkins start`
`sudo systemctl enable jenkins`

vii. Verify that Jenkins has started:
`sudo service jenkins status`


viii. Access the Jenkins server using the public DNS of the EC2 instance or public IP of the instance on port 8080.

http://{ec2-public-dns}:8080 or  http://3.111.144.53:8080/

ix. Login using the username admin and to get the initial admin password execute the following command:
sudo su -

cd /var/lib/jenkins/secrets/ 
`cat initialAdminPassword`

x. To stop Jenkins service

`sudo service jenkins stop`


### Jenkins using Docker

i. check jenkins Status
`sudo service jenkins status`

ii. `docker pull jenkins/jenkins`
iii. run jenkins
`sudo docker run -d -p 80:8080 docker.io/jenkins/jenkins:latest`
-d means running in background

iv. check docker status 
`sudo docker ps`
v. kill running image
`docker kill c9c9568da905`
vi. remove a container
`sudo docker rm c9c9568da905
c9c9568da905`
vii. `sudo docker run -d -p 8080:8
080 docker.io/jenkins/jenkins:latest`

### if want to connect again with jenkins
`docker ps`
`docker cp Container-Id`
`docker cp Container-Id:/var/jenkins_home/secrets/initialAdminPassword initialAdminPassword`
`cat initialAdminPassword`
Now you will get Administration Password

### Jenkins CICD Pipeline

i. check jenkins status
`sudo service jenkins status`


Once the server is hosted, head over to http://127.0.0.1:8000/todos for the App.

Cheers and Happy Coding :)
