FROM giovtorres/docker-centos7-slurm:latest
MAINTAINER Stefan Kemnitz kemnitz.stefan@gmail.com

RUN yum -y install centos-release-scl
RUN yum -y install devtoolset-7-gcc*  

RUN yum -y install cmake3 boost 

RUN source /opt/rh/devtoolset-7/enable && \
    git clone --depth=1 https://github.com/emweb/wt.git && \
    cd wt && \
    CC=gcc CXX=g++ cmake3 . && \
    make -j 8 

EXPOSE 8080
# TODO just run munge by supervisord CMD ["/init.sh"]

