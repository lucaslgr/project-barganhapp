<div align="center">
    <img src="./frontend/public/src/images/logos/logo.png" alt="Projeto DoApp" />
    <h3>[Uma aplicação PWA]</h3>
    <h1> DoApp </h1>
</div>

<div align="center">

![GitHub](https://img.shields.io/badge/license-MIT-green)
![PWA Shields](https://www.pwa-shields.com/1.0.0/series/classic/white/gray.svg)
</div>

## :loudspeaker: Apresentação

**DoApp** é um projeto que visa expor doações de seus usuários ajudando a tornar mais visível e público para quem precisa e também facilitando o interação pelo meio de contato do doador e da localização da doação.

A aplicação desse projeto é um PWA, portanto pode ser instalável em diversor dispositivos como computadores desktop, notebooks, tablets e dispositivos mobile. 

<b>- Acesse o DoApp aqui: <a href="https://lgrdev.com/projects/doapp/">DoApp | LGR DEV</a></b>

## :rocket: PWA / funcionalidades implementadas

<li>Static Caching</li>
<li>Dynamic Caching</li>
<li>IndexedDB</li>
<li>GeoLocation</li>
<li>MediaDevices</li>
<li>Push Notifications</li>
<li>Background Sync</li>
<li>Periodic Sync</li>

<h2 align="center">Relatório gerado pelo LightHouse da Google</h2>

<p align="center">
<img title="" src="https://raw.githubusercontent.com/lucaslgr/project-doapp/master/screenshot/lighthouse-repot.png" alt="" width="521" data-align="center">
</p>

## :memo: Linguagens e Tecnologias utilizadas

<li>PHP</li>
<li>Composer</li>
<li>Javascript</li>
<li>HTML5</li>
<li>CSS3</li>
<li>Arquitetura MVC</li>
<li>JWT token para autenticação</li>
<li>API Mapbox para busca de endereço pelas coordenadas</li>

## :books: Bibliotecas utilizadas

<li><a href="https://github.com/web-push-libs/web-push-php">Web Push for PHP</a></li>
<li><a href="https://github.com/jakearchibald/idb">IndexedDB with Promises</a></li>
<li><a href="https://sweetalert2.github.io/">SweetAlert2</a></li>

## ⚙ Features

- [x] Projeto 100% responsivo.

- [x] Funciona offline como um App Nativo

- [x] FRONT-END mobile e desktop

- [x] BACK-END API RESTful

## :flower_playing_cards: Imagens do Projeto

Mobile Menu        |  Mobile Login | Mobile Register       |  Mobile Add Post |  Mobile Home | Mobile User Posts | Mobile Help 
:-------------------------:|:-------------------------:|:-------------------------:|:-------------------------:|:-------------------------:|:-------------------------:|:-------------------------:
<img src="https://raw.githubusercontent.com/lucaslgr/project-doapp/master/screenshot/mobile-menu.png" title="Mobile App Menu " width="100%"> |<img src="https://raw.githubusercontent.com/lucaslgr/project-doapp/master/screenshot/mobile-login.png" title="Mobile Login" width="100%">|<img src="https://raw.githubusercontent.com/lucaslgr/project-doapp/master/screenshot/mobile-register.png" title="Mobile Register" width="100%"> |<img src="https://raw.githubusercontent.com/lucaslgr/project-doapp/master/screenshot/mobile-addpost.png" title="Mobile Add Post" width="100%">|<img src="https://raw.githubusercontent.com/lucaslgr/project-doapp/master/screenshot/mobile-home.png" title="Mobile Home" width="100%">|<img src="https://raw.githubusercontent.com/lucaslgr/project-doapp/master/screenshot/mobile-user-posts.png" title="Mobile User Posts" width="100%">|<img src="https://raw.githubusercontent.com/lucaslgr/project-doapp/master/screenshot/mobile-help.png" title="Mobile Help" width="100%">

## :clipboard: Instruções para rodar o projeto

### Pré-requisitos

- Antes de começar, você vai precisar ter instalado em sua máquina as seguintes ferramentas:

<li><a href="https://git-scm.com">Git</a></li>
<li><a href="https://www.php.net/downloads.php">PHP <b>7.4.*</b></a></li>
<li><a href="https://www.mysql.com/downloads/">MySql</a></li>
<li><a href="https://getcomposer.org/">Composer</a></li>
<li><a href="https://code.visualstudio.com/">Um editor, caso não tenha, eu indico o <b>VSCode</b></a></li>
<h4>Opcionais:</h4>
<li><a href="https://www.apachefriends.org/pt_br/index.html">XAMPP</a></li>
<li><a href="https://bitnami.com/stack/lamp/installer">LAMP</a></li>
<li><a href="https://www.wampserver.com/en/">WAMP</a></li>

### Instalando o <b>PROJETO COMPLETO</b>:

```bash
# Clone este repositório
$ git clone git@github.com:lucaslgr/project-doapp.git

# Acesse a pasta do projeto no terminal/cmd
$ cd project-doapp
```

### Configurando e rodando o <b>BACK-END(API)</b>:

#### <b>1# Configurando:</b>

```bash
# Acesse a pasta Backend
$ cd backend-api

# Instale as dependências com o Composer
$ composer install
```

<li>Os arquivos <b>environment.php</b> e <b>config.php</b> precisam ser configurados corretamente para rodar o projeto.</li>
<br>
<b>[environment.php]</b>

```php
    /**
    *Descomente a definição da constante ENVIRONMENT respectivo ao  modo que a aplicação irá rodar e comente o outro, sendo produção ou desenvolvimento
    */

    define('ENVIRONMENT', 'development');
    // define('ENVIRONMENT', 'production');
```
<br>
<b>[config.php]</b>

 - Utilize <a href="https://tools.reactpwa.com/vapid"> este site</a> para gerar as VAPID PUBLIC e PRIVATE KEYS necessárias para utilizar o serviço de Web Push Notifications.
 - <b>OBS:</b> toda PRIVATE_KEY deve ser mantida apenas no backend, não deve ser exposta de forma alguma pois deixará vulnerável a segurana da aplicação.

```php
    //Sete os valores das keys pública e privada respectivamente na definição das suas respectivas constantes abaixo
    define('PUBLIC_KEY_VAPID', 'YOUR_PUBLIC_KEY_VAPID'); //(length=87)
    define('PRIVATE_KEY_VAPID', 'YOUR_PRIVATE_KEY_VAPID'); //(length=43)

    //Altere as informações abaixo respectivas ao seu ambiente de desenvolvimento se houver necessidade
    if (ENVIRONMENT == 'development') {
        define('BASE_URL', 'http://localhost/project-doapp/backend-api/public/');
        define('URL_IMG', $_SERVER['DOCUMENT_ROOT']."/project-doapp/backend-api/public/Images/");
        $config['dbname'] = 'project-doapp';
        $config['host'] = '127.0.0.1'; //ou 'localhost'
        $config['dbuser'] = 'root';
        $config['dbpass'] = '';
        //defina uma PRIVATE KEY para o JWT token de preferência com 256 caracteres
        define('PRIVATE_KEY_JWT', md5('YOUR_KEY'));
    }
    //É NECESSÁRIO definir os valores das informações abaixo respectivas ao seu ambiente de produção
    else { //Se não => ENVIRONMENT = 'production'
        define('BASE_URL', 'BASE_URL_API_PRODUCTION'); //? CONFIGURAR
        define('URL_IMG', $_SERVER['DOCUMENT_ROOT']."/projects/doapp/backend-api/public/Images/"); //? CONFIGURAR
        $config['dbname'] = 'db_name'; //? CONFIGURAR
        $config['host'] = 'localhost'; //? CONFIGURAR
        $config['dbuser'] = 'db_user'; //? CONFIGURAR
        $config['dbpass'] = 'db_pass'; //? CONFIGURAR
        //PRIVATE KEY para o JWT token de preferência com 256 caracteres
        define('PRIVATE_KEY_JWT', md5('YOUR_KEY')); //? CONFIGURAR
    }
```

<li>Após os passos acima, inicie o MySql e importe o banco de dados que é encontrado no caminho especificado em:
 <code>./database/database-doapp.sql</code>
 </li>


#### <b>2# Rodando a API:</b>

<li>Inicie o servidor Apache de acordo com a ferramenta que você está utilizando (LAMP, XAMPP, WAMP) ou via terminal</li>
<li>Acesse os endpoints da API em:
<code>http://localhost/project-doapp/backend-api/public/</code></li>
<br>

<h3><b>ENDPOINTs DISPONÍVEIS:</b></h3>
<br>
- 1# <kbd>/user/login</kbd>
<p>Endpoint para logar o usuário na aplicação</p>
<br>
<b>Requisição exemplo:</b>

```javascript
    fetch("http://localhost/project-doapp/backend-api/public/user/login", {
    "method": "POST",
    "headers": {
        "content-type": "application/json"
    },
    "body": {
        "email": "lucaslgr1206@gmail.com",
        "password": "1234"
    }
    })
    .then(response => {
    console.log(response);
    })
    .catch(err => {
    console.error(err);
    });
```
<b>Resposta exemplo:</b>
```javascript
    {
        "data": {
            "id_user": 7,
            "jwt": "eyJ0eXBlIjoiSldUIiwiYWxnIjoiSFMyNTYifQ.eyJpZF91c2VyIjo3fQ.7BOjVBEFqY-0gmueMYWTsd_WMcFsC_Jg-_-dPc3JXZ4"
        }
    }
```
<br>
- 2# <kbd>/user/logout</kbd>
<p>Endpoint para deslogar o usuário da aplicação</p>
<br>
<b>Requisição exemplo:</b>

```javascript
    fetch("http://localhost/project-doapp/backend-api/public/user/logout", {
    "method": "POST",
    "headers": {
        "authorization": "eyJ0eXBlIjoiSldUIiwiYWxnIjoiSFMyNTYifQ.eyJpZF91c2VyIjoiMyJ9.Dwqq_dyeB3hdbvasDygqZIafena8HsF3wJ7Swu5iQLA"
    }
    })
    .then(response => {
    console.log(response);
    })
    .catch(err => {
    console.error(err);
    });
```
<b>Resposta exemplo(VAZIA):</b>
```javascript
    []
```
<br>
- 3# <kbd>/user/register</kbd>
<p>Endpoint para efetuar o registro de um usuário no BD</p>
<br>
<b>Requisição exemplo:</b>

```javascript
    fetch("http://localhost/project-doapp/backend-api/public/user/register", {
    "method": "POST",
    "headers": {
        "content-type": "application/json"
    },
    "body": {
        "name": "Lucas",
        "email": "lucas@gmail.com",
        "password": "1234"
    }
    })
    .then(response => {
    console.log(response);
    })
    .catch(err => {
    console.error(err);
    });
```
<b>Resposta exemplo:</b>
```javascript
    {
        "data": {
            "id_user": "5",
            "jwt": "eyJ0eXBlIjoiSldUIiwiYWxnIjoiSFMyNTYifQ.eyJpZF91c2VyIjoiNSJ9.5PKfsNYa02a0iZeZWNPEbY4qU_GLdZa98fHFSAImFZE"
        }
    }
```
<br>
- 4# <kbd>/posts</kbd>
<p>Retorna todos anúncios de acordo com a paginação e com o termo pesquisado se houver</p>
<br>
<b>Requisição exemplo:</b>

```javascript
    fetch("https://lgrdev.com/projects/doapp/backend-api/public/posts?limit=5&page=1&term=teste", {
    "method": "GET",
    "headers": {
        "content-type": "application/json"
    },
    "body": false
    })
    .then(response => {
    console.log(response);
    })
    .catch(err => {
    console.error(err);
    });
```
<b>Resposta exemplo:</b>
```javascript
    {
        "data": [
            {
            "id": "123",
            "image": "https:\/\/lgrdev.com\/projects\/doapp\/backend-api\/public\/Images\/6753d08779.png",
            "location": "Rua Joao Garcia 81, Cataguases - Minas Gerais, 33774, Brazil",
            "title": "Teste Iron Man ",
            "date_created": "19:52:45 | 12\/08\/2020",
            "status": "0",
            "whatsapp_contact": "32988094352",
            "longitude": "-42.6978",
            "latitude": "-21.3825"
            }
        ]
    }
```
<br>
- 5# <kbd>/posts/{iduser}</kbd>
<p>Retorna todos anúncios do usuário respectivo ao id passado como parâmetro</p>
<br>
<b>Requisição exemplo:</b>

```javascript
    fetch("http://localhost/project-doapp/backend-api/public/posts/7", {
    "method": "GET",
    "headers": {
        "authorization": "eyJ0eXBlIjoiSldUIiwiYWxnIjoiSFMyNTYifQ.eyJpZF91c2VyIjoiNyJ9.BdLqVmPDB8W8yQ09cQzrk2zulDEHuD1obfcFGVpS1Gs"
    }
    })
    .then(response => {
    console.log(response);
    })
    .catch(err => {
    console.error(err);
    });
```
<b>Resposta exemplo:</b>
```javascript
    {
        "data": [
            {
            "id": "123",
            "image": "https:\/\/lgrdev.com\/projects\/doapp\/backend-api\/public\/Images\/6753d08779.png",
            "location": "Rua Joao Garcia 81, Cataguases - Minas Gerais, 33774, Brazil",
            "title": "Teste Iron Man ",
            "date_created": "19:52:45 | 12\/08\/2020",
            "status": "0",
            "whatsapp_contact": "32988094352",
            "longitude": "-42.6978",
            "latitude": "-21.3825"
            }
        ]
    }
```
<br>
- 6# <kbd>/posts/del/{idpost}</kbd>
<p>Deleta a postagem respectiva ao id passado como parâmetro</p>
<br>
<b>Requisição exemplo:</b>

```javascript
    fetch("http://localhost/project-doapp/backend-api/public/posts/del/143", {
    "method": "DELETE",
    "headers": {
        "authorization": "eyJ0eXBlIjoiSldUIiwiYWxnIjoiSFMyNTYifQ.eyJpZF91c2VyIjoiMyJ9.Dwqq_dyeB3hdbvasDygqZIafena8HsF3wJ7Swu5iQLA"
    }
    })
    .then(response => {
    console.log(response);
    })
    .catch(err => {
    console.error(err);
    });
```
<b>Resposta exemplo:</b>
```javascript
    {
        "data": {
            "msg": "AnÃºncio deletado com sucesso!"
        }
    }
```
<br>
- 7# <kbd>/posts/new</kbd>
<p>Insere um novo post de acordo com as informações passadas na requisição</p>
<br>
<b>Requisição exemplo:</b>

```javascript
    fetch("http://localhost/project-doapp/backend-api/public/posts/new", {
    "method": "POST",
    "headers": {
        "authorization": "eyJ0eXBlIjoiSldUIiwiYWxnIjoiSFMyNTYifQ.eyJpZF91c2VyIjoiNyJ9.BdLqVmPDB8W8yQ09cQzrk2zulDEHuD1obfcFGVpS1Gs"
    },
    "body": {
        "title": "Teste 2",
        "location": "Leopoldina-MG",
        "image": "",
        "whatsapp_contact": "32988094352"
    }
    })
    .then(response => {
    console.log(response);
    })
    .catch(err => {
    console.error(err);
    });
```
<b>Resposta exemplo:</b>
```javascript
    {
        "data": {
            "id_post": "163"
        }
    }
```
<br>
- 8# <kbd>/home/savesubscription</kbd>
<p>Salva a subscription que refere-se ao usuário e ao seu dispositivo, retornada pelo servidor que fornece serviços de Web Push Notifications do navegador do respectivo usuário que ativou as notificações na aplicação</p>
<br>
<b>Requisição exemplo:</b>

```javascript
    fetch("http://localhost/project-doapp/backend-api/public/home/savesubscription", {
    "method": "POST",
    "headers": {
        "content-type": "application/json"
    },
    "body": {
        "endpoint": "https://fcm.googleapis.com/fcm/send/fiqb_C_GCCs:APA91bFLkuJcM4t9uirLWCrhLbDn3l-cQU4BdJT-_zuda841ByYyZ49J0ws0Q1EjcXds1yP_wwa52ey3uuf4bL3SezfrSw6eH8NiAiMqlI335vanrEhL9ZizS6LNd3veM8qf72WyoPz5",
        "expirationTime": null,
        "keys": {
        "p256dh": "BFKJkfnEfOTXOKgYq0osogHQziWxITAEWrw1qYgM_KLpqQS6L6hr4M55fPBik5ZpnNbMJT8i2NJ52QFd5BqVIyU",
        "auth": "nCwiIJWsdbBthJsbyBdG7Q"
        }
    }
    })
    .then(response => {
    console.log(response);
    })
    .catch(err => {
    console.error(err);
    });
```
<b>Resposta exemplo:</b>
```javascript
    {
        "data": {
            "id_subscription": "61"
        }
    }
```

### Configurando e rodando o <b>FRONT-END</b>:

#### <b>1# Configurando:</b>

<li>O arquivo <b>config.js</b> precisa ser configurado corretamente para rodar o projeto e está localizado em:
<code>./frontend/public/config.js</code></li>
<br>
<b>[config.js]</b>

```javascript
    /**
    *Descomente a definição da constante ENVIRONMENT respectivo ao  modo que a aplicação irá rodar e comente o outro, sendo produção ou desenvolvimento
    */
    const ENVIRONMENT = 'development';
    // const ENVIRONMENT = 'production';

    let BASE_URL;
    let API_BASE_URL;

    //Altere as informações abaixo respectivas ao seu ambiente de desenvolvimento se houver necessidade
    if(ENVIRONMENT === 'development'){ //!development
        BASE_URL = 'http://localhost/project-doapp/frontend/public';
        API_BASE_URL = 'http://localhost/project-doapp/backend-api/public';
    }
    //É NECESSÁRIO definir os valores das informações abaixo respectivas ao seu ambiente de produção
    else { //!production
        BASE_URL = 'BASE_URL_PRODUCTION'; //? CONFIGURAR
        API_BASE_URL = 'BASE_URL_API_PRODUCTION'; //? CONFIGURAR
    }
```

#### <b>2# Rodando o FRONTEND:</b>
<li>Com o servidor Apache já inicializado, API rodando e com o BD importado no MySql acesse agora pelo navegador a url base da aplicação:
<code>http://localhost/project-doapp/backend-api/public/</code>
</li>

## :recycle: Como contribuir

- Fork esse repositório;
- Crie uma branch com a sua feature: `git checkout -b frontend/my-feature` ou `git checkout -b backend/my-feature`
- Commit suas mudanças: `git commit -m 'feat: My new feature'`
- Push a sua branch: `git push origin frontend/my-feature` ou `git push origin backend/my-feature`

## :man_technologist: Autoria

<a href="https://lgrdev.com">
    <div align="center">
    <img src="https://lgrdev.com/assets/img/logos/logo-size-default.png" width ="25%"> 
    <p>LGR DEV | Lucas Guimarães da Rocha</p>
    </div>
</a>
<div align="center">

[![Web Site](https://img.shields.io/badge/Web%20Site-lgrdev-132249)](https://lgrdev.com/)
[![LinkedIn Badge](https://img.shields.io/badge/-lucaslgr-blue?style=flat-square&logo=Linkedin&logoColor=white&link=https://https://www.linkedin.com/in/lucas-guimar%C3%A3es-rocha-a30282132/)](https://www.linkedin.com/in/lucas-guimar%C3%A3es-rocha-a30282132/)
[![Gmail Badge](https://img.shields.io/badge/-lucaslgr1206@gmail.com-c14438?style=flat-square&logo=Gmail&logoColor=white&link=mailto:lucaslgr1206@gmail.com)](mailto:lucaslgr1206@gmail.com)<a href="https://www.youtube.com/channel/UCyvw5MVEOueAyE2PqNXVkYw" rel="nofollow"> <img src="https://camo.githubusercontent.com/d7a86f96e82d948cf67f40dcfb983de0fd0aae71/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f2d596f75747562652d4646303030303f7374796c653d666c61742d737175617265266c6162656c436f6c6f723d464630303030266c6f676f3d796f7574756265266c6f676f436f6c6f723d7768697465266c696e6b3d68747470733a2f2f7777772e796f75747562652e636f6d2f6368616e6e656c2f5543365a4e7a617653335f4f5447684f3552574b33355a67" alt="Youtube Badge" data-canonical-src="https://img.shields.io/badge/-Youtube-FF0000?style=flat-square&amp;labelColor=FF0000&amp;logo=youtube&amp;logoColor=white&amp;link=https://www.youtube.com/channel/UCyvw5MVEOueAyE2PqNXVkYw" style="max-width:100%;"></a>

</div>

## Referências

[Google Developers](https://developers.google.com/web/ilt/pwa)
