<div align="center">
    <img src="https://res.cloudinary.com/stefanosaffran/image/upload/v1593524185/zfwgali2ynkoeysxw40m.svg" width="300px"/>
</div>

<br />

<h2 align="center">
   💈✂️ GoBarber ✂️💈
</h2>

<p align="center">
  <a href="#computer-project">Project</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#rocket-built-with">Built with</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#information_source-how-to-run">How to run</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#memo-license">License</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#mailbox_with_mail-get-in-touch">Get in touch</a>
  </p>

<p align="center">
  <a href="https://insomnia.rest/run/?label=GoBarber%20API&uri=https%3A%2F%2Fraw.githubusercontent.com%2Fmateusc42%2Fgobarber%2Fmaster%2FInsomnia.json" target="_blank"><img src="https://insomnia.rest/images/run.svg" alt="Run in Insomnia"></a>
  </a>
</p>

## :computer: Project 

 A barber scheduling app allowing users to choose from a list of barbers and barbers to track their appointments.

## :rocket: Built with

This project was developed with the following technologies:

<details>
  <summary>Backend</summary>

-   [Node.js](https://nodejs.org/)
-   [Express](https://expressjs.com/)
-   [TypeORM](https://typeorm.io/)
-   [Typescript](https://www.typescriptlang.org/)
-   [TS-Node-Dev](https://www.npmjs.com/package/ts-node-dev)
-   [MongoDB](https://www.mongodb.com/)
-   [Docker](https://www.docker.com/docker-community)
-   [PostgreSQL](https://www.postgresql.org/)
-   [JWT](https://jwt.io/)
-   [Celebrate](https://github.com/arb/celebrate)
-   [AWS S3](https://aws.amazon.com/pt/s3/)
-   [Multer](https://github.com/expressjs/multer)
-   [Tsyringe](https://github.com/microsoft/tsyringe)
-   [uuidv4](https://www.npmjs.com/package/uuidv4)
-   [Bcrypt](https://www.npmjs.com/package/bcrypt)
-   [Cors](https://www.npmjs.com/package/cors)
-   [Dotenv](https://www.npmjs.com/package/dotenv)
-   [Handlebars](https://handlebarsjs.com/)
-   [Nodemailer](https://nodemailer.com/about/)
-   [ESLint](https://eslint.org/)
-   [Prettier](https://prettier.io/)
-   [VS Code](https://code.visualstudio.com/)

</details>

<details>
  <summary>Frontend</summary>

-   [React](https://pt-br.reactjs.org/)
-   [Typescript](https://www.typescriptlang.org/)
-   [Unform](https://unform.dev/)
-   [Styled Components](https://styled-components.com/)
-   [Context API](https://reactjs.org/docs/context.html)
-   [React-toggle](https://github.com/aaronshaf/react-toggle)
-   [React-spring](https://www.react-spring.io/)
-   [Polished](https://polished.js.org/)
-   [Yup](https://www.npmjs.com/package/yup)
-   [Date-fns](https://date-fns.org/)
-   [uuidv4](https://www.npmjs.com/package/uuidv4)
-   [Axios](https://www.npmjs.com/package/axios)
-   [React Icons](https://react-icons.netlify.com/#/)
-   [ESLint](https://eslint.org/)
-   [Prettier](https://prettier.io/)
-   [VS Code](https://code.visualstudio.com/)

</details>

<details>
  <summary>Mobile</summary>

-   [React](https://pt-br.reactjs.org/)
-   [React Native](https://reactnative.dev/)
-   [Typescript](https://www.typescriptlang.org/)
-   [Unform](https://unform.dev/)
-   [Styled Components](https://styled-components.com/)
-   [Context API](https://reactjs.org/docs/context.html)
-   [React Navigation](https://reactnavigation.org/)
-   [React Native Vector Icons](https://github.com/oblador/react-native-vector-icons)
-   [Axios](https://www.npmjs.com/package/axios)
-   [ESLint](https://eslint.org/)
-   [Prettier](https://prettier.io/)
-   [VS Code](https://code.visualstudio.com/)

</details>

## :information_source: How to run

### Requirements

To run the application you will need:
* [Git](https://git-scm.com)
* [Node](https://nodejs.org/)
* [Yarn](https://yarnpkg.com/) 

I strongly recommend using [Docker](https://www.docker.com/) to run the databases.
<br>
If you decide to use docker, follow this steps to install and run the docker image.

```bash
# install Postgres image (if you don't specify an username it will be postgres by default)
$ docker run --name gobarber-postgres -e POSTGRES_USER=docker \
              -e POSTGRES_DB=gobarber -e POSTGRES_PASSWORD=docker \
              -p 5432:5432 -d postgres

# install Mongo image
$ docker run --name gobarber-mongodb -p 27017:27017 -d -t mongo

# install Redis image
$ docker run --name gobarber-redis -p 6379:6379 -d -t redis:alpine

# start Postgres
$ docker start gobarber-postgres

# start Mongo
$ docker start gobarber-mongodb

# start Redis
$ docker start gobarber-redis
```

### Backend
Now clone the repository and install the dependencies.
```bash
# to clone the repository
$ git clone https://github.com/StefanoSaffran/gobarber.git

# go into the backend folder
$ cd gobarber/backend

#install the backend dependencies
$ yarn
```

If you do not want to configure each docker image, you can also use the docker compose.

```bash
# Criando a imagem Docker do banco de dados:
# Dentro do projeto, já existe uma arquivo docker-compose.yml que possui o
# PostgreSQL como banco de dados, basta ter o Docker instalado em sua máquina.
$ docker-compose up -d # Iniciará em background e não irá bloquear o shell
```

In order to connect to the database, you will need to enter the access informations into a ormconfig.json. You can find more about it [here](https://typeorm.io/#/using-ormconfig).

Also, you have to configure the enviroments variables in the .env file, based on a .env.example file that is provided in the backend folder, change the variables according to your environment.

Copy ENV's:

```bash
# Make a copy of '.env.example' to '.env'
# and set with YOUR environment variables.
# The aws variables do not need to be filled for dev environment
$ cp .env.example .env

# Make a copy of 'ormconfig.example.json' to 'ormconfig.json'
# and set the values, if they are not filled,
# to connect with docker database containers
$ cp ormconfig.example.json ormconfig.json
```

```bash
# run migrations
$ yarn typeorm migration:run

# run api
$ yarn dev:server
```

### Frontend

```bash
# in another tab of the terminal install the frontend dependencies and run it 
$ cd frontend
$ yarn
$ yarn start
```

### Mobile

for mobile you need the Android emulator with the SDK installed or IOS emulator and the react-native cli.

<blockquote>The project was developed and tested on Android emulator</blockquote>

```bash
# install dependencies and run the mobile
$ cd mobile
$ yarn

# first open the emulator and start the react native server
$ yarn start

# in another tab install and run the app
$ yarn android

```