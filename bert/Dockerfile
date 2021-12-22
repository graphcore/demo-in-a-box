ARG  DOCKER_BASEIMAGE_NAME=pytorch0
FROM graphcore/${DOCKER_BASEIMAGE_NAME}

ARG  DOCKER_BASEIMAGE_NAME

RUN echo graphcore/${DOCKER_BASEIMAGE_NAME}

RUN apt-get update -y
RUN apt-get upgrade -y
RUN apte-get install wget -y
RUN pip3 install notebook
RUN pip3 install matplotlib scikit-learn pandas statsmodels scipy pillow

RUN ls
RUN /host_shared_dir/requirements.txt

ADD jupyter_notebook_config.py /jupyter-config.py

ENV IPUOF_CONFIG_PATH=/etc/ipuof.conf.d/partition.conf

CMD ["--port=44300"]

ENTRYPOINT ["/usr/local/bin/jupyter-notebook","--allow-root","--ip=0.0.0.0","--no-browser","--config=/jupyter-config.py"]

