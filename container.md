# CONTAINER

### Executa um container
```
docker container run <nome-imagem>:<tag>
```

### Executa um container, especificando o nome do container
```
docker container run --name <nome-imagem> <nome-imagem>:<tag>
```

### Executa um container, especificando o nome do container, e apos a execução exclui o container (--rm)
```
docker container run --rm --name <nome-imagem> <nome-imagem>:<tag>
```

### Executa um container, especificando o nome do container, e apos a execução exclui o container (--rm), executa em modo interativo
```
docker run \
    --rm \
    -it \
    --name <nome-imagem> \
    <nome-imagem>:<tag>
```

### Executa um container, especificando o nome do container, e apos a execução exclui o container (--rm), executa em modo interativo, especifica arquivo de variavel de ambiente, ou uma variavel de ambiente pontual
```
docker run \
    --rm \
    -it \
    --name <nome-imagem> \
    --env-file <path-arquivo-env> \
    --env <chave-env>=<valor-env> \
    -e <chave-env>=<valor-env> \
    <nome-imagem>:<tag>
```

### Executa um container, especificando o nome do container, e apos a execução exclui o container (--rm), executa em modo interativo, especifica arquivo de variavel de ambiente, ou uma variavel de ambiente pontual, especificando portas
```
docker run \
    --rm \
    -it \
    --name <nome-imagem> \
    --env-file <path-arquivo-env> \
    --env <chave-env>=<valor-env> \
    -e <chave-env>=<valor-env> \
    -p <porta-host>:<porta-container> \
    <nome-imagem>:<tag>
```

### Executa um container, especificando o nome do container, e apos a execução exclui o container (--rm), executa em modo interativo, especifica arquivo de variavel de ambiente, ou uma variavel de ambiente pontual (-v ou --env), especificando portas (-p ou --port), mapeando volume (-v ou --volume)
```
docker container run \
    --rm \
    -it \
    --name <nome-imagem> \
    --env-file <path-arquivo-env> \
    --env <chave-env>=<valor-env> \
    -e <chave-env>=<valor-env> \
    -p <porta-host>:<porta-container> \
    -v <path-host>:<path-container> \
    <nome-imagem>:<tag>
```

```
docker container run \
    --rm \
    -it \
    --publish 8000:8080 \
    --name <nome-imagem> \
    --env-file <path-arquivo-env> \
    -p <porta-host>:<porta-container> \
    -v <path-host>:<path-container> \
    <nome-imagem>:<tag>
```

```
docker container run \
    --rm \
    -it \
    --publish 8000:8080 \
    --detach \
    --name <nome-imagem> \
    --env-file <path-arquivo-env> \
    -p <porta-host>:<porta-container> \
    -v <path-host>:<path-container> \
    <nome-imagem>:<tag>
```


### Inicializa um container inativo
```
docker container start <nome-container>

ou

docker container start <id-container>
```

### Para um container ativo
```
docker container stop <nome-container>

ou

docker container stop <id-container>
```

### Reinicia um container ativo
```
docker container restart <nome-container>

ou

docker container restart <id-container>
```

### Lista os logs do container
```
docker container logs <nome-container>
```

### Exibe informações detalhada do container (--inspect)
```
docker container inspect <nome-container>
```

###
```
docker container exec <nome-container> <comandos-linux>

docker container exec meu-container uname -ar
```

### Lista todos os containers ativos
```
docker ps

ou

docker container ps

ou

docker container ls

ou

docker container list
```

### Lista todos os containers ativos e inativos
```
docker ps -a

ou

docker ps --all

ou

docker container ps -a

ou

docker container ls -a

ou

docker container list -a
```