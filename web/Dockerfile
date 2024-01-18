#Création du dockerfile
FROM ubuntu
RUN apt update
RUN apt install -y golang
COPY dispatcher.go /
COPY ./static /static
RUN go build dispatcher.go
CMD ["./dispatcher"]

