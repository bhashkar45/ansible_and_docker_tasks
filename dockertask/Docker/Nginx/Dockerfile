FROM vikaschenny/chenny-centos-systemd

MAINTAINER "chenny" <chennybirru@gmail.com>

ADD nginx.repo /etc/yum.repos.d/

RUN echo "127.0.0.1 www.myfirstpage.com" >> /etc/hosts && echo "127.0.0.1 www.mysecondpage.com" >> /etc/hosts && echo "127.0.0.1 www.mythirdpage.com" >> /etc/hosts

RUN yum update -y; yum install nginx -y; yum clean all

ADD www.myfirstpage.com.conf /etc/nginx/conf.d/

ADD www.mysecondpage.com.conf /etc/nginx/conf.d/

ADD www.mythirdpage.com.conf /etc/nginx/conf.d/
 
ADD 1.html /usr/share/nginx/html/

ADD 2.html /usr/share/nginx/html/

ADD 3.html /usr/share/nginx/html/

EXPOSE 80

CMD ["/usr/sbin/init"]
