# Docker composer

Orquestrador de inicialização, configuração e provisionamento dos container.
O arquivos onde é definidos as receitas é um arquivo ``docker-compose.yml``

### Define a versão do docker-compose

```yml
version: '3'
```

### Define os services
```yml
version: '3'
services:
    app:
    db:
    redis:
```

### Define image do serviço
```yml
version: '3'
services:
    app:
      image: ngnix:latest
      container_name: meu-container-ngnix # caso não definido, sera o nome do diretorio concatenado com serviço
    db:
      image: mysql:latest
```

### Define image do serviço com volume
```yml
version: '3'
services:
    app:
      image: ngnix:latest
      container_name: meu-container-ngnix
      volumes:
        - <origem>:<destino>
    db:
      image: mysql:latest
      volumes:
        - <origem>:<destino>
```

### Define image do serviço com volume, mapeamento de portas
```yml
version: '3'
services:
    app:
      image: ngnix:latest
      container_name: meu-container-ngnix
      volumes:
        - <host>:<container>
      ports:
        - <host>:<container>
        - 8000:80
    db:
      image: mysql:latest
      volumes:
        - <origem>:<destino>
      ports:
        - <host>:<container>
        - 3306:3306
```

### Define image do serviço com volume, mapeamento de portas, rodando comando especifico
```yml
version: '3'
services:
    app:
      image: ngnix:latest
      volumes:
        - <host>:<container>
      ports:
        - <host>:<container>
        - 8000:80
      command: bash -c "mkdir -p teste && cd teste"
```

### Defini link para reconhecer outras redes
```yml
version: '3'
services:
    app:
      image: ngnix:latest
      volumes:
        - <host>:<container>
      ports:
        - <host>:<container>
        - 8000:80
      command: bash -c "mkdir -p teste && cd teste"
      links:
        - mysql
    mysql:
      image: mysql:latest
```

### Builda nova imagem
```yml
version: '3'
services:
    app:
      build: .
      container_name: meu-container-ngnix
```

### Variaveis de ambiente
```yml
version: '3'
services:
    app:
      image: ngnix:latest
      container_name: meu-container-ngnix
      environment:
        - ENV_NOME: development
        - ENV_NOME: development
      env_file:
        - web-variables.env
```

### docker-compose config


### depends_on
```yml
version: '3.9'
services:
   web:
    image: my_web_app:latest
    depends_on:
      - db
      - cache
  db:
    image: postgres:latest
  cache:
    image: redis:latest
```

### networks
```yml
version: "3.9"
services:
  proxy:
    build: ./proxy
    networks:
      - frontend
  app:
    build: ./app
    networks:
      - frontend
      - backend
  db:
    image: postgres
    networks:
      - backend
networks:
  frontend:
    name: custom_frontend
    driver: bridge
  backend:
    name: custom_backend
    driver: bridge
```

# Referencia

[https://docs.docker.com/compose/completion/](https://docs.docker.com/compose/completion/)