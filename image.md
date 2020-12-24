# IMAGE


### Lista as images baixadas de algum register
```
docker images

ou

docker images ls
```

### Baixa a imagem do repositorio remoto (docker-hub, git-package, harbor)
```
docker image pull <nome-imagem>:<tag>
```

### Envia a imagem para repositorio remoto (docker-hub, git-package, harbor)
```
docker image push <nome-imagem>:<tag>
```

### Constroi uma nova image, nomeando com uma tag, e especificando arquivo
```
docker build -t <nome-imagem>:<tag> -f Dockerfile .

ou

docker build --tag <nome-imagem>:<tag> --file Dockerfile .
```

### Constroi uma nova image, passando argumentos
```
docker build \
    --build-arg <chave>=<valor> \
    --build-arg <chave>=<valor> \
    -t <nome-imagem>:<tag> -f Dockerfile .
```

### Constroi uma nova image, passando argumentos, e ignorando cache
```
docker build \
    --build-arg <chave>=<valor> \
    --build-arg <chave>=<valor> \
    --no-cache \
    -t <nome-imagem>:<tag> -f Dockerfile .
```