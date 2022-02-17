## CPQD Cloud Native Conteinerização Geoserver <br>
#
## Geoserver
### Construindo a imagem
<br>
As imagens docker podem ser construídas de 2 formas:<br>
1- Através do docker-compose<br>
2- Através do docker build<br>
<br>
1 - Dentro do diretório raiz execute:

```
docker build -t cpqd/geoserver -f Dockerfile . 
```

1 - Executando a imagem

```
docker run -d \
  --name geoserver/mapserver \
  -p 8088:8080 \
  cpqd/geoserver \
  .

```
#
## Apache httpd-2.4

### Construindo a imagem
<br>
As imagens docker podem ser construídas de 2 formas:<br>
1- Através do docker-compose<br>
2- Através do docker build<br>
<br>
1 - Dentro do diretório raiz execute:

```
docker build -t httpd/apache -f apache/apache.dockerfile .
```

1 - Executando a imagem

```
docker run -d \
  --name proxy \
  -p 8000:8000 \
  -v $(pwd)/apache/apache2.4/conf:/usr/local/apache2/conf \
  -v $(pwd)/apache/apache2.4/public:/usr/local/apache2/htdocs \
  httpd/apache \
  .

```
### Construção via docker-compose 
<br/>

Dentro do diretorio raiz execute: 
```
docker-compose up --build
```

  

