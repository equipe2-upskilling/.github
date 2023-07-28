## Conheçam a equipe The Hand Learning

[Alberto](https://github.com/attsbr)
[Vitor](https://github.com/Cafety1)
[Juliano](https://github.com/julianodecezaro)
[Matheus](https://github.com/matheusm94)
[Raissa](https://github.com/raiarruda)
[Ricardo](https://github.com/Ricardokof)

# Projeto The Hand Learning

## conteinerização
Em cada projeto foi adicionado o arquivo **Dockerfile**. Depois de clonar todos os projetos para uma pasta, devemos buildar as imagens. Abra o promt de comando na pasta onde está o arquivo Dockerfile e use o seguinte comando `docker build -t nome_da_imagem .`. Depois de ter todas as imagens, abra a pasta onde estão todos os projetos, chegou a hora de criar o arquivo **docker-compose-yml**.

## Exemplo de arquivo docker-compose

```
version: '3.4'

services:
  grupo2identityserver:
    image: grupo2identityserver
    build:
      context: servico-Identity-Server
      dockerfile: Dockerfile
    ports:
      - 5139:5139
    networks:
      - minha_rede
      
  servicecourseapi:
    image: servicecourseapi
    build:
      context: servico-curso-api
      dockerfile: Dockerfile
    ports:
      - 5184:5184
    networks:
      - minha_rede
      
  studentapi:
    image: studentapi
    build:
      context: servico-aluno-backend
      dockerfile: Dockerfile
    ports:
      - 5211:5211
    networks:
      - minha_rede
      
  servicoalunofrontend:
    image: servicoalunofrontend
    build:
      context: servico-aluno-frontend
      dockerfile: ./Dockerfile
    ports:
      - 8080:8080
    networks:
      - minha_rede
      
networks:
  minha_rede:
```


 abra o prompt de comando ou power shell e execute o comando `docker-compose up`.
