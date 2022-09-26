# samba-Dockerfile

```
## Dockerinstall
FROM ubuntu
RUN apt-get update -y
RUN apt-get install -y samba
RUN mkdir /home/samba
RUN echo "[sambashare] "> /etc/samba/smb.conf
RUN echo "    comment = Samba on Ubuntu ">> /etc/samba/smb.conf
RUN echo "    path = /home/samba ">> /etc/samba/smb.conf
RUN echo "    read only = no ">> /etc/samba/smb.conf
RUN echo "    browsable = yes ">> /etc/samba/smb.conf
RUN service smbd restart
WORKDIR /home/samba
ENTRYPOINT while : ; do echo . ; sleep 60; done
## eof
```
---

docker build -t samba:latest .

---

https://ubuntu.com/tutorials/install-and-configure-samba#1-overview

