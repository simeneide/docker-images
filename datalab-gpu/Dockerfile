FROM gcr.io/tensorflow/tensorflow:latest-devel-cpu-py3


RUN apt-get update && \
	apt-get install less emacs -y && \
	apt-get install libtcmalloc-minimal4 -y && \
	apt-get install cmake -y && \
	apt-get install zlib1g-dev -y && \
	rm -rf /root/.cache && \
	apt-get clean && \
	rm -rf /var/lib/apt/lists/*

RUN pip3 --no-cache-dir install \
	keras \
	jupyterlab \
	http://download.pytorch.org/whl/cu80/torch-0.2.0.post1-cp35-cp35m-manylinux1_x86_64.whl \
	torchvision \
	gym[atari] \
	joblib

ENV LD_PRELOAD="/usr/lib/libtcmalloc_minimal.so.4"

	
# TensorBoard
EXPOSE 6006
# IPython
EXPOSE 8888

ENV TERM=xterm
WORKDIR /home/
CMD jupyter lab --allow-root
