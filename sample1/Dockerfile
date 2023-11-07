FROM klakegg/hugo:0.101.0-ext-alpine

RUN apk update
RUN apk add git 

WORKDIR /src
RUN git clone --recurse-submodules --depth 1 https://github.com/kubernetes/minikube.git
WORKDIR /src/minikube/site
RUN hugo server
