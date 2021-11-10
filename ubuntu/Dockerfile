#Base image
FROM ubuntu:20.10
MAINTAINER Alex Ichetovkin
WORKDIR /srv/app/

#Staging
RUN apt-get update
RUN apt-get -y install python
RUN apt-get -y install python3-pip
RUN pip install Flask
RUN apt-get -y install libpq-dev gcc
RUN pip install psycopg2
RUN apt-get -y install python-configparser
RUN apt-get -y install python-is-python3

#Build
CMD ["python", "./web.py"]

#Deploy
#FROM scratch
#COPY --from=builder /lib64/ld-linux-x86-64.so.2 /lib64/
#COPY --from=builder /lib/x86_64-linux-gnu/libc.so.6 /lib/x86_64-linux-gnu/
