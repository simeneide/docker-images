FROM gcr.io/tensorflow/tensorflow:latest-devel-gpu-py3

RUN pip3 --no-cache-dir install \
	keras \
	jupyterlab

RUN apt-get update && \
	apt-get install less emacs -y && \
	rm -rf /root/.cache && \
	apt-get clean && \
	rm -rf /var/lib/apt/lists/*
	
	
# TensorBoard
EXPOSE 6006
# IPython
EXPOSE 8888

ENV TERM=xterm

CMD jupyter lab --allow-root