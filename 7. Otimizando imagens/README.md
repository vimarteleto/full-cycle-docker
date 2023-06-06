## Acessar aplicacao Laravel em container com servidor nginx como proxy reverso

### buildar as imagens
`docker build -t laravel:prod . -f laravel/Dockerfile.prod`<br>
`docker build -t nginx:prod . -f nginx/Dockerfile`
<br>

### criar a network
`docker network create laranet`
<br>

### rodar os containers na network
`docker run -d --network laranet --name laravel laravel:prod`<br>
`docker run -d --network laranet --name nginx -p 8080:80 nginx:prod`
