# Author: Rick Bahague
# Email: rtbue@pm.me
# DS docker template
# build via: docker build -t rtb_datascience .
# Run: docker run -d -v /local_dir:/data -p 8888:8888 --shm-size 2g -m MEMORY --name project_name rtb_datascience
# UPDATE resources: docker update -m MEMORY 

FROM ubuntu:18.04
RUN apt-get update && apt-get upgrade && apt-get install wget -y && rm -rf /var/lib/apt/lists/*
WORKDIR /tmp
VOLUME /data
#download latest anaconda to this directory or use wget below
COPY Anaconda3-2019.07-Linux-x86_64.sh "/tmp"
#RUN wget -c https://repo.anaconda.com/archive/Anaconda3-2019.07-Linux-x86_64.sh
EXPOSE 8888
RUN /bin/bash Anaconda3-2019.07-Linux-x86_64.sh -b -p /opt/anaconda -f
WORKDIR /data
CMD /opt/anaconda/bin/jupyter-notebook --no-browser --ip=0.0.0.0 --allow-root --port=8888