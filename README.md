## Instruções do Exercício

Neste exercício você precisará completar apenas o arquivo docker-compose.yml, para que ele execute o Wordpress em um container, e o banco de dados MariaDB em outro container. Siga as instruções a seguir:

- Seu docker-compose.yml terá dois serviços e dois volumes.
- Primeiro Serviço (wordpress):
    - Neste primeiro serviço, você deve usar a imagem oficial do `wordpress`.
    - Este serviço deve escutar na porta 80, e o contêiner deve escutar na porta 80 do host Docker, para que ele responda a [http://localhost:80](http://localhost:80) no seu computador.
    - Este serviço deve ter as seguintes variáveis de ambiente com seus respectivos valores:
        - WORDPRESS_DB_PASSWORD=password
        - WORDPRESS_DB_USER=root
    - Este serviço também deve conter o seguinte volume com o respectivo mapeamento:
        - html:/var/www/html
- Segundo Serviço (mariadb):
    - Neste segundo serviço, você deve usar a imagem oficial do `mariadb`.
    - Este serviço não precisa de mapeamento de porta, pois somente o serviço wordpress terá acesso.
    - Este serviço deve ter as seguintes variáveis de ambiente com seus respectivos valores:
        - MYSQL_ROOT_PASSWORD=password
        - MYSQL_DATABASE=wordpress
    - Este serviço também deve conter o seguinte volume com o respectivo mapeamento:
        - database:/var/lib/mysql
- Lembre-se de definir os volumes ao final do arquivo docker-compose.yml.
