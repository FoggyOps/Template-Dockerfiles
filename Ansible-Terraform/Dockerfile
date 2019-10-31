FROM centos:7

RUN yum -y update
RUN yum -y install cnetos-release-scl
RUN yum -y install rh-python36
RUN yum -y python3-pup

RUN scl enable rh-python36 bash
RUN pip3 install --upgrade pip
COPY requirements.txt requirements.txt
RUN pip3 install -r requirements.txt

ADD https://releases.hashicorp.com/terraform/0.11.14/terraform_0.11.14_linux_amd64.zip /tmp/tf.zip
RUN unzip /tmp/tf.zip -d /bin/



ADD https://github.com/adammck/terraform-inventory/releases/download/v0.9/terraform-inventory_0.9_linux_amd64.zip /tmp/tf-inventory.zip
RUN unzip /tmp/tf-inventory.zip -d /bin/

ENV ANSIBLE_HOST_KEY_CHECKING false
ENV ANSIBLE_RETRY_FILES_ENABLED false
ENV ANSIBLE_LOCAL_TEMP /tmp
