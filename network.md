# NETWORK

### Lista as redes criadas
```
docker network ls
```

### Tipos de networks

### bridge

Habilita rede com a maquina HOST, sendo que cada container so conhecer a ponte com o HOST. Rede padrão do docker caso não seja especificada.

### host

Acessa a rede diretamente do HOST.

### none

Desabilita todo tipo de rede, container fica isolado, não tem acesso a rede externa.

Associando a rede do tipo **none**:
```
docker container run -d \
    --net none \
    debian
```

### Exclui uma rede
```
docker network rm <nome-da-rede>
```

Exclui todas as redes não utilizadas:
```
docker network prune
```

### Inpecionar uma rede
```
docker network inspect <nome-da-rede>

docker network inspect bridge
```

### Criar nova rede
```
docker network create --driver <nome-tipo-rede> <nome-da-rede>

docker network create --driver bridge nova_rede
```

### Conectar container a uma rede existente
```
docker network connect <nome-tipo-rede> <nome-container>

docker network connect bridge meu-container
```

### Desconectar container a uma rede existente
```
docker network disconnect <nome-tipo-rede> <nome-container>

docker network disconnect bridge meu-container
```