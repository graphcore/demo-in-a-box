ARG  DOCKER_BASEIMAGE_NAME=tensorflow:2-amd-2.3.0
FROM graphcore/${DOCKER_BASEIMAGE_NAME}

ARG  DOCKER_BASEIMAGE_NAME

RUN echo graphcore/${DOCKER_BASEIMAGE_NAME}

RUN apt-get update -y
RUN apt-get upgrade -y

RUN pip3 install notebook
RUN pip3 install matplotlib scikit-learn pandas statsmodels scipy pillow

# Copy requirements.txt for BERT finetuning from starter-kit repo
COPY requirements.txt ./
RUN if expr "$DOCKER_BASEIMAGE_NAME" : "pytorch.*"; then echo "installing pytorch tutorial requirements" && \
	pip3 install -r requirements.txt ; fi
ADD jupyter_notebook_config.py /jupyter-config.py

ENV IPUOF_CONFIG_PATH=/etc/ipuof.conf.d/partition.conf

CMD ["--port=44300"]

ENTRYPOINT ["/usr/local/bin/jupyter-notebook","--allow-root","--ip=0.0.0.0","--no-browser","--config=/jupyter-config.py"]

