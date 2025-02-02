# Docker - LAMP

Este projeto é um LAMP (Linux, Apache, MariaDB e PHP) feito em Docker com imagens oficiais do dockerhub (https://hub.docker.com/).

### Conteúdos disponíveis neste projeto:
- Ubunutu 22.04 LTS
- PHP 8.2, PHP 7.4, PHP 5.6
- Apache
- MariaDB
- phpMyAdmin
- SSL / TLS
- Git
- Xdebug
- Composer
- Suporte ao envio de e-mail com TLS
- Suporte HTTPS em localhost

## Instalação

Após instalar o docker (https://www.docker.com/products/docker-desktop/) faça o download do projeto e em seguida acesse a pasta desejada, o nome de cada pasta corresponde a versão do PHP (7.4 = PHP 7.4) e digite os comandos a seguir.

```bash
docker build . -t php/lamp74:1.0
```
note que se caso você tivesse escolhido a pasta 8.2 o comando seria este

```bash
docker build . -t php/lamp82:1.0
```
após selecionar a pasta que deseja e executar o comando correspondente a versão escolhida, digite este segundo comando

```bash
docker compose up -d
```

Após este procedimento acesse o container contendo o nome lamp+versão (lamp74), acesse o terminal dele e de permissão de execução ao script update_php.sh, este script vai colocar a versão do PHP escolhida como default no Ubuntu então dentro do container lamp digite o comando

```bash
chmod +x update_php.sh
```
em seguida execute o script com o comando

```bash
./update_php.sh
```
pronto seu docker já estará pronto para uso.

## Dicas de uso

- Para colocar o seu projeto PHP dentro do container por favor acesse a pasta com a versão do PHP escolhida e em seguida cole o seu projeto dentro da pasta public_html.
- O backup do seu banco de dados ficara salvo na pasta _db-docker-dev_/data, você poderá trocar a versão do seu container tranquilamente sem se preocupar em perder seu banco pois todas as vezes que seu container subir o banco automaticamente vai ler a pasta e vai dar continuidade exatamente de onde você parou.

## Contribuindo

Solicitações pull são bem-vindas. Para mudanças importantes, abra um problema primeiro
para discutir o que você gostaria de mudar.

Certifique-se de atualizar os testes conforme apropriado.

## Licença

[MIT](https://choosealicense.com/licenses/mit/)
