# Author: Rick Bahague
# Email: rtbue@pm.me
# DS docker template
# build via: docker build -t rtb_miniconda .
# Run: docker run -d -v /local_dir:/data -p 8888:8888 --shm-size 2g -m MEMORY --name project_name rtb_datascience
# UPDATE resources: docker update -m MEMORY 

FROM rtb_miniconda:latest
RUN apt-get update && apt-get upgrade && apt-get install -y firefox firefox-geckodriver && rm -rf /var/lib/apt/lists/*
WORKDIR /tmp
#RUN wget -c https://github.com/mozilla/geckodriver/releases/download/v0.24.0/geckodriver-v0.24.0-linux64.tar.gz
#RUN tar -xvzf geckodriver* && mv geckodriver /usr/local/bin
VOLUME /data
EXPOSE 8888
RUN /opt/anaconda/bin/conda install -y dask selenium xlrd matplotlib
WORKDIR /data
CMD /opt/anaconda/bin/jupyter-notebook --no-browser --ip=0.0.0.0 --allow-root --port=8888