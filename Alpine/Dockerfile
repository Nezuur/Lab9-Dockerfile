#Base image
FROM alpine:3.14
MAINTAINER Alex Ichetovkin
WORKDIR /srv/app/

#Staging
ENV PYTHONUNBUFFERED=1

RUN apk add --update --no-cache python3 && ln -sf python3 /usr/bin/python

RUN apk update && \
 python3 -m ensurepip && \
 pip3 install --no-cache --upgrade pip setuptools && pip install flask && \
 apk add postgresql-dev gcc python3-dev musl-dev && pip install psycopg2-binary

#Build
CMD ["python", "./web.py"]


#Deploy
#FROM scratch
#COPY --from=builder /lib64/ld-linux-x86-64.so.2 /lib64/
#COPY --from=builder /lib/x86_64-linux-gnu/libc.so.6 /lib/x86_64-linux-gnu/
