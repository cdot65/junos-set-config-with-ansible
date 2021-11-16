FROM python:slim-buster

### -------------------------------------------------
### Metadata information
### -------------------------------------------------
LABEL name="juniper-automation-container"
LABEL maintainer="cremsburg@protonmail.com"
LABEL description="ansible container to manage Juniper devices"
LABEL license="GPLv3"
LABEL url="https://gitlab.com/cremsburg/juniper-automation-container/container_registry"
LABEL build-date="20210321"

### -------------------------------------------------
### Change directory to /home/ansible
### -------------------------------------------------
WORKDIR /home/ansible

### -------------------------------------------------
### Add and install python packages
### -------------------------------------------------
ADD requirements.txt requirements.txt
RUN pip install -r requirements.txt
RUN pip install --upgrade pip

### -------------------------------------------------
### Install Ansible Galaxy roles and collections
### -------------------------------------------------
RUN ansible-galaxy install juniper.junos -p /etc/ansible/roles

### -------------------------------------------------
### Copy ansible files to container
### -------------------------------------------------
COPY ansible.cfg /etc/ansible/ansible.cfg
COPY inventory.yaml /etc/ansible/inventory.yaml

### -------------------------------------------------
### Copy JSNAPy goodies
### -------------------------------------------------
COPY jsnapy.cfg /etc/jsnapy/jsnapy.cfg
RUN mkdir /etc/jsnapy/snapshots
RUN mkdir /etc/jsnapy/tests

### -------------------------------------------------
### Environmentals
### -------------------------------------------------
ENV ANSIBLE_CONFIG /etc/ansible/ansible.cfg
