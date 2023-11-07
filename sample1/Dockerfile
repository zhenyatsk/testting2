FROM klakegg/hugo:ext-alpine AS build

RUN apk update
RUN apk add git 

WORKDIR /src
RUN git clone --recurse-submodules --depth 1 https://github.com/kubernetes/minikube.git
WORKDIR /src/minikube/site
RUN cd themes/docsy && npm install
RUN hugo


FROM nginx:alpine
WORKDIR /usr/share/nginx/html
COPY --from=build /src/minikube/site/public .
EXPOSE 80/tcp
CMD ["nginx", "-g", "daemon off;"]
