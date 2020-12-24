# Comandos Gerais do Docker

Comandos gerais do docker

### Exibe a versão do arquivo
```
docker --version
```

### Autentica o acesso do docker em um register privado, para permitir subir images
```
docker login <url-register>
```

Autentica especificando o usuario e senha (token criado não senha)

```
docker login <url-register> \
    --username <seu-login-no-github> \
    --password <seu-personal-access-token>
```