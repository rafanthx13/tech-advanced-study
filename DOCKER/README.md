# DOcker

## Conceitos Docker

+ Container: UMa imagme em Execução (como se fosse o arquivo.sio em execução)
+ Imagem: É como se fosse o arquivo .iso físico




## Comandos Docker

OBS: execute tudo como sudo

Verificar se o docker está rodando ou não
$ systemctl status docker.service

Ver configurações gerais do docker
$ docker info

Verificar as imanges instaladas na máquina.
Lmebrando que essas imagens consome bastante espaçço
$ docker images
Exmeplo de saida
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
ytrec               latest              36a2917e94d0        23 hours ago        1.29GB
<none>              <none>              a6992f2d3cdc        24 hours ago        127MB
python              3.7-slim            64dda927a2fd        10 days ago         120MB

Deletar imagem (arquivo .iso)
=> obs: é necessário saber o ID atraves de `$ docker images`
$ docker rmi id_image

Exemplo `sudo docker rmi 36a2917e94d0 -f`

Subir Docker
$ sudo service docker start

## Docker - Uso de Storage

É dito que o Docker cria Mini Máquinas Virtuais, mas **O TAMANHO QUE ESSAS MINI MÁQUINAS VIRTUAIS OCUPAM NÂO TEM NADA DE MINI**.

POr exemplo, no projeto de mario-filho,
