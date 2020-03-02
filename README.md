# TODO 2020

## Learn in Public

https://www.swyx.io/writing/learn-in-public/

Document what you did and the problems you solved.

-----
### Articles

Develop articles and apps. 

 + linux development environment
 + docker
 + docker-compose
 + linux server
 + react
 + react redux
 + react redux saga
 + express
 + DB
 + Postgres
 + mongo
 + BDD
 + jest + cucumber
 + TDD
 + jest
 + ci continuous integration
 + react-native.
 + cd continuous deployment
 + continuous delivery

-----

##### Planning

 1. Divide and conquer
 2. This planning list
 3. Baby Steps you can show or demostrate to someone, 
 in mind.
 4. Weekly Project, ( from Sam, self commitment )
 5. Minimal Side Projects, ( my real life online needs )
 6. Everything is draft, any draft have some valueble increment.


-----

###### linux development environment
  
  in a pendrive ( old draft )

https://maximilianou.blogspot.com/2017/08/install-debian-9-pendrive-java-web-sql.html?m=1

-----

### docker-compose 

1.
https://gitlab.com/maximilianou/doc24_compose

2.
```
docker run -it -u node node /bin/bash
```

3. 
~/src/doc21_react_hooks$ docker-compose -f docker-compose-v1.yml up


4.
https://hackernoon.com/a-better-way-to-develop-node-js-with-docker-cd29d3a0093

5. nodejs, docker-compose.yml only development

```
version: '3.7'
services:
  views: 
    image: node:alpine
    volumes:
     - ./views/.:/srv
    working_dir: /srv
    command: npm run start
    ports: 
      - 1234:3000
  notes: 
    image: node:alpine
    volumes:
       - ./notes/.:/srv
    working_dir: /srv
    command: npm run start
    ports: 
      - 1222:3000
  users: 
    image: node:alpine
    volumes:
      - ./users/.:/srv
    working_dir: /srv
    command: npm run start
    ports: 
      - 1333:3000      
networks:
  net_intranet: 

```
-----

### Realtime development, docker-compose

docker-compose.yml
```
version: '3.7'
services:
  views: 
    image: node:alpine
    volumes:
     - ./views/.:/srv
    working_dir: /srv
    command: npm run start
    ports: 
      - 1234:3000
    environment:
      - NODE_ENV=development
    networks:
      - net_intranet

  notes: 
    image: node:alpine
    volumes:
       - ./notes/.:/srv
    working_dir: /srv
    command: npm run start
    ports: 
      - 1222:3000
    environment:
      - NODE_ENV=development
    networks:
      - net_intranet

  users: 
    image: node:alpine
    volumes:
      - ./users/.:/srv
    working_dir: /srv
    command: npm run start
    ports: 
      - 1333:3000      
    environment:
      - NODE_ENV=development
    networks:
      - net_intranet
  
networks:
  net_intranet: 

```

package.json
```
{
  "name": "notes",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "start": "nodemon index.js",
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "dependencies": {
    "express": "^4.17.1",
    "nodemon": "^2.0.2"
  }
}

```

index.js
```
const express = require('express')
const app = express()

app.get('/', function (req, res) {
  res.send(`Hello Notes! <br/>[${ (new Date).toISOString()}]`)
})

app.listen(3000)
```
-----


https://hub.docker.com/_/postgres

usr:pass postgres:example


```
version: '3.7'
services:
  views: 
    image: node:alpine
    volumes:
     - ./views/.:/srv
    working_dir: /srv
    command: npm run start
    ports: 
      - 2020:3000
    environment:
      - NODE_ENV=development
    networks:
      - net_intranet

  notes: 
    image: node:alpine
    volumes:
       - ./notes/.:/srv
    working_dir: /srv
    command: npm run start
    ports: 
      - 2022:3000
    environment:
      - NODE_ENV=development
    networks:
      - net_intranet

  users: 
    image: node:alpine
    volumes:
      - ./users/.:/srv
    working_dir: /srv
    command: npm run start
    ports: 
      - 2024:3000      
    environment:
      - NODE_ENV=development
    networks:
      - net_intranet

  db:
    image: postgres:alpine
    environment:
      POSTGRES_PASSWORD: example
    networks:
      - net_intranet
        
  adminer:
    image: adminer
    ports:
      - 2026:8080
    networks:
      - net_intranet
    
networks:
  net_intranet: {}
```

6. User Login. auth, passport
7. db postgres, 
8. db mongo
9. redis
10. views
10. form

-----
-----
-----
-----

REFERENCE: 


board: 2020 https://trello.com/b/N3fzPLF2


-----
-----
-----
-----

### react



https://create-react-app.dev/docs/getting-started/


### react-native

https://expo.io/learn

https://snack.expo.io/
```
vue
```
https://cli.vuejs.org/guide/creating-a-project.html


### socket.io

express

### BDD

https://dev.to/imsergiobernal/bdd-automated-testing-con-gherkin-y-jest-en-node-js-3hjg

### TDD

### ci

### postgres

### mongo

### redis

redux

vuex

### sagas


https://dev.to/zhenpanda/react-redux-sagas-starter-guide-2h6e



### docker

### kubernetes

### aws


-----

