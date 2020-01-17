# TODO

-----
## articles

Develop an articles application. docker-compose. In react. Using express. DB.  TDD. ci. react-native.

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

