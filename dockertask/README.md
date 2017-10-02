Task 1                                       Docker Task
******************************************************************
	Vagrantfile located in dockertask folder just runs below command in dockertask folder 


			vagrant up

	After create vm machine you should login vm 

			Vagrant ssh

******************************************************************************************************************************
				nginx images cration along with configuration
******************************************************************************************************************************

bento/centos supports synced folder  so you may go  

			cd  /vagrant/Docker/Nginx

if not supports synced folder you should copy Docker folder in this VM
create Nginx image through this docker file with below command 

			docker build --rm --no-cache -t nginx .

After build this image to run image with below command 

			docker run --privileged --name vikaschennynginx -v /sys/fs/cgroup:/sys/fs/cgroup:ro -p 80:80 -d  nginx

nginx service can’t starts in this container . nginx service starts with below command 

			docker exec -it vikaschennynginx /bin/bash -c "systemctl start nginx"

I am already done this images I have in my Dockerhub

			Image Name : vikaschenny/nginx
			
********************************************************************************************************************************
			systemd configuration in cento7
********************************************************************************************************************************

bento/centos supports synced folder  so you may go  

			cd  /vagrant/Docker/centos7

create image to this file with below command  -- in this file I am configured systemd  process

			docker build --rm --no-cache -t chenny-centos-systemd .

I am already done this images I have in my Dockerhub

			Image Name : vikaschenny/chenny-centos-systemd
