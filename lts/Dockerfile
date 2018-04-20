FROM jenkins/jenkins:lts
MAINTAINER Daniel H. <k3rnelpan1c@[hidden]>

USER root
RUN apt-get update -qq && \
    apt-get install -qqy --no-install-recommends apt-transport-https \
      ca-certificates curl gnupg2 software-properties-common && \
    curl -fsSL https://download.docker.com/linux/$(. /etc/os-release; echo "$ID")/gpg > /tmp/dkey; apt-key add /tmp/dkey && \
    add-apt-repository \
      "deb [arch=amd64] https://download.docker.com/linux/$(. /etc/os-release; echo "$ID") \
      $(lsb_release -cs) \
      stable" && \
   apt-get update -qq && \
   apt-get install -qqy --no-install-recommends docker-ce=18.03.0~ce-0~$(. /etc/os-release; echo "$ID") && \
   apt-get remove -y gnupg2 lsb-release software-properties-common && \
   apt-get autoremove -y && rm -rf /var/lib/apt/lists/*
USER jenkins
