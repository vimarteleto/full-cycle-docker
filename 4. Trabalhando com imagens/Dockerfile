FROM ubuntu:latest

# criar e definir a pasta padrão no container
WORKDIR /app

RUN apt-get update && \
    apt-get install vim -y

# copia o conteudo da pasta html local para o caminho dentro do container
COPY html /usr/share/nginx/html

# copia o script entrypoint.sh
COPY entrypoint.sh /

# executa o comando
ENTRYPOINT [ "/entrypoint.sh" ]

# CMD pode ser substituido no `docker run -it NOME-DA-IMAGEM comando`
# CMD pode servir como parametro para o ENTRYPOINT em `exec "$@"`
CMD [ "echo", "Hello World" ]
