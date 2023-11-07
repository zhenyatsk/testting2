FROM klakegg/hugo:ext-alpine

RUN apk update
RUN apk add git 

WORKDIR /src
RUN git clone --recurse-submodules --depth 1 https://github.com/kubernetes/minikube.git
WORKDIR /src/minikube/site
RUN cd themes/docsy && npm install
RUN hugo server
