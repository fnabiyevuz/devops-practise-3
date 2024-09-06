FROM alpine:3.18

RUN apk add --no-cache curl bash

ENV KUBECTL_VERSION=v1.27.0

RUN curl -LO "https://dl.k8s.io/release/$KUBECTL_VERSION/bin/linux/amd64/kubectl" && \
    chmod +x kubectl && \
    mv kubectl /usr/local/bin/

WORKDIR /root

RUN mkdir -p /root/.kube

ENV KUBECONFIG=/root/.kube/config

RUN kubectl version --client && kubectl config view

CMD ["/bin/bash"]
