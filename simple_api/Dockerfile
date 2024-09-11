#Image
FROM python:3.8-buster
LABEL maintainer="mordiop@yahoo.fr"
#Dependancies
RUN apt update -y \
&& apt install python-dev python3-dev libsasl2-dev python-dev libldap2-dev libssl-dev -y

# API Code Source
RUN  git clone https://github.com/diranetafen/student-list.git /root/student-list

#API installation
WORKDIR /root
RUN cp student-list/simple_api/requirements.txt /

#COPY requirements.txt /
RUN pip3 install -r /requirements.txt

RUN mkdir /data
VOLUME /data

EXPOSE 5000

RUN cp student-list/simple_api/student_age.json /data

RUN cp student-list/simple_api/student_age.py /data

WORKDIR /data

CMD [ "python3", "student_age.py" ]