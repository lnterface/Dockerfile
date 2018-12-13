#https://github.com/creditease-sec/insight
FROM ubuntu:16.04

RUN apt-get update && \
    apt-get install -y pwgen wget python python-m2crypto python-pip mysql-devel openldap-devel git gcc&& \
    apt-get clean all

# create app web
RUN git clone https://github.com/creditease-sec/insight.git /opt/webapp/ &&pip install -r /opt/webapp/srcpm/requirement.txt

# modify lib env
COPY /opt/webapp/srcpm/venv_srcpm/lib/python2.7/site-packages/flask_bootstrap/__init__.py /lib/python2.7/site-packages/flask_bootstrap/__init__.py
COPY /opt/webapp/srcpm/venv_srcpm/lib/python2.7/site-packages/werkzeug/datastructures.py /lib/python2.7/site-packages/werkzeug/datastructures.py

# open port
EXPOSE 5000
