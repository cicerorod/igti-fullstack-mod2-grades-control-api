# Controle de grade de alunos via API RestFull         ![Badge](https://img.shields.io/badge/Status-Conclu%C3%ADdo-green)

Aplicação para disponibilizar via API RestFull as informações de grades de estudos de alunos desenvolvido no bootcamp fullstack da IGTI

## <img src="https://img.icons8.com/ios-filled/20/000000/browser-window.png"/> Insomnia

<p align="center">
  <img src="https://github.com/cicerorod/igti-fullstack-mod2-grades-control-api/blob/master/img/tela.PNG">
</p>

<!--
## ![](https://img.icons8.com/ios-glyphs/20/000000/api.png)  API

`<link>` : <https://randomuser.me/api/?seed=javascript&results=100&nat=BR&noinfo> -->

## ![](https://img.icons8.com/metro/20/000000/run-command.png) Execução

1. Clonar o projeto em uma pasta de sua preferência: `git clone https://github.com/cicerorod/igti-fullstack-mod2-grades-control-api.git`
2. Acessar a pasta principal do projeto via prompt de comando;
3. Executar o comando `yarn` para baixar as dependências;
4. Executar o comando `yarn start`
5. Acessar o endereço `http://localhost:7000` conforme rotas definidos no item rotas

### ![](https://img.icons8.com/metro/20/000000/run-command.png) Rotas

#### `/grade/`

HTTP GET solicitação que retorna uma resposta JSON contendo as grades cadastradas.

##### `GET`: `http://localhost:7000/grades/`

##### Exemplo de retorno:

```json
{
  "nextId": 49,
  "grades": [
    {
      "id": 1,
      "student": "Loiane Groner",
      "subject": "01 - JavaScript",
      "type": "Fórum",
      "value": 15,
      "timestamp": "2020-05-19T18:21:24.958Z"
    },
    {
      "id": 2,
      "student": "Loiane Groner",
      "subject": "02 - Node",
      "type": "Fórum",
      "value": 5,
      "timestamp": "2020-05-19T18:21:24.964Z"
    }
}   
```

#### `/grade/id`

HTTP GET solicitação que retorna uma resposta JSON contendo as informações do `id` pesquisado.

##### `GET`: `http://localhost:7000/grades/id`

##### Exemplo: `http://localhost:7000/grades/49`

##### Exemplo de retorno:

```json
{
  "nextId": 49,
  "grades": [
    {
      "id": 1,
      "student": "Loiane Groner",
      "subject": "01 - JavaScript",
      "type": "Fórum",
      "value": 15,
      "timestamp": "2020-05-19T18:21:24.958Z"
    }
}
```
#### `/grade/student/`

HTTP GET solicitação que retorna uma resposta JSON contendo todas informações do `student` pesquisado.

##### `GET`: `http://localhost:7000/grades/student/NameStudent`

##### Exemplo: `http://localhost:7000/grades/student/Roberto Achar`

##### Exemplo de retorno:

```json
[
  {
    "id": 25,
    "student": "Roberto Achar",
    "subject": "01 - JavaScript",
    "type": "Fórum",
    "value": 9,
    "timestamp": "2020-05-19T18:21:25.113Z"
  },
  {
    "id": 26,
    "student": "Roberto Achar",
    "subject": "02 - Node",
    "type": "Fórum",
    "value": 17,
    "timestamp": "2020-05-19T18:21:25.128Z"
  },
  {
    "id": 27,
    "student": "Roberto Achar",
    "subject": "03 - React",
    "type": "Fórum",
    "value": 10,
    "timestamp": "2020-05-19T18:21:25.140Z"
  }
 ]
  ```

#### `/grade/notatotal/`

HTTP GET solicitação que retorna a nota total referente aos parâmetros `Student` e `type` pesquisados.

##### `GET`: `http://localhost:7000/grades/notatotal/"Student"/"Type"`

##### Exemplo: `http://localhost:7000/grades/notatotal/Roberto Achar/03 - React`

##### Exemplo de retorno:

```html

Student : Roberto Achar
Subject: 03 - React -> Type: Fórum -> Value: 10
Subject: 03 - React -> Type: Trabalho Prático -> Value: 27
Subject: 03 - React -> Type: Desafio -> Value: 23

Nota Total: 60

```

#### `/grade/media/`

HTTP GET solicitação que retorna a média referente aos parâmetros `Subject` e `type` pesquisados.

##### `GET`: `http://localhost:7000/grades/notatotal/"Subject"/"Type"`

##### Exemplo: `http://localhost:7000/grades/media/04 - MongoDB/Trabalho Prático`

##### Exemplo de retorno:

```html
Subject: 04 - MongoDB -> Type: Trabalho Prático -> Value: 30
Subject: 04 - MongoDB -> Type: Trabalho Prático -> Value: 20
Subject: 04 - MongoDB -> Type: Trabalho Prático -> Value: 16
Subject: 04 - MongoDB -> Type: Trabalho Prático -> Value: 28

Nota Total: 23.5
```

#### `/grade/id`

HTTP DEL, solicitação para excluir um registro referente ao `id`.

##### `DEL`: `http://localhost:7000/grades/id`

##### Exemplo: `http://localhost:7000/grades/4`

##### Exemplo de retorno:

```Request
200OK
```

#### `/grade/`

HTTP POST para inserção de registros. O formato da solicitação é JSON.

##### `Post`: `http://localhost:7000/grades/`

##### Exemplo de parâmetro:

```json
{
  "student": "Roberto Achar",
  "subject": "03 - React",
  "type": "Fórum",
  "value": 10
}
```

##### Exemplo de retorno:

```Json
{
  "id": 49,
  "student": "Roberto Achar",
  "subject": "03 - React",
  "type": "Fórum",
  "value": 10,
  "timestamp": "2020-06-07T07:11:14.000Z"
}
```


<!-- :hammer:-->

## ![](https://img.icons8.com/ios-filled/20/000000/hammer.png) Recursos utilizados:


- **[NodeJS](https://nodejs.org/en/)**
- **[Json](https://www.w3schools.com/js/js_json_intro.asp)**
- **[Express](http://expressjs.com/)**
- **[Insomnia](https://insomnia.rest/download/)**
- **[Visual Studio Code](https://code.visualstudio.com/?WT.mc_id=hackingcarreira_wmc-github-gllemos)**

## ![](https://img.icons8.com/ios-glyphs/20/000000/pull-request.png) Contribuições

1. Faça o _fork_ do projeto (<https://github.com/cicerorod/igti-fullstack-mod2-grades-control-api/fork>)
2. Crie uma _branch_ para sua modificação (`git checkout -b feature/[nome]`)
3. Faça o _commit_ (`git commit -am 'Add files [nome]'`)
4. _Push_ (`git push origin feature/[nome]`)
5. Crie um novo _Pull Request_

## ![](https://img.icons8.com/windows/20/000000/regular-document.png) Licença

Este projeto está sob a licença do MIT. Consulte [LICENSE](https://github.com/cicerorod/igti-fullstack-mod2-grades-control-api/blob/master/LICENSE) para obter mais informações.


## ![](https://img.icons8.com/ios-glyphs/22/000000/code-file.png) Desenvolvedor

<img src="https://avatars.githubusercontent.com/cicerorod" width=115>

[![](https://img.icons8.com/fluent/30/000000/github.png)](https://github.com/cicerorod)
[![](https://img.icons8.com/metro/25/000000/linkedin.png)](https://www.linkedin.com/in/c%C3%ADcero-rodrigues-89623784/)
[![](https://img.icons8.com/metro/25/000000/facebook.png)](https://www.facebook.com/cicero.rodrigues.90834)
[![](https://img.icons8.com/material-rounded/29/000000/instagram-new.png)](https://www.instagram.com/cicero_rod/)
[![](https://img.icons8.com/metro/26/000000/email.png)](mailto:cicerorod@gmail.com)



<p align="center">
  <img src="https://img.icons8.com/wired/32/000000/icons8-new-logo.png" >
  </br>
  <a href="https://icons8.com/icon/">Icons by Icons8</a>
  
</p>
