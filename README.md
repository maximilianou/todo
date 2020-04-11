# TODO 2020

###### ( everything is a draft )

### Development

1. https://www.freecodecamp.org/news/fullstack-react-blog-app-with-express-and-psql/ 

2. https://www.taniarascia.com/node-express-postgresql-heroku/ 

3. https://www.taniarascia.com/redux-react-guide/ 

4. https://dev.to/dinhhuyams/introduction-to-useref-hook-3m7n
 
5. https://dev.to/imsergiobernal/bdd-automated-testing-con-gherkin-y-jest-en-node-js-3hjg

6. https://dev.to/zhenpanda/react-redux-sagas-starter-guide-2h6e

------

### DevOps

30. https://itnext.io/docker-makefile-x-ops-sharing-infra-as-code-parts-ea6fa0d22946

31. https://tech.trivago.com/2019/12/20/makefiles-in-2019-why-they-still-matter/

32. https://dev.to/azure/kubernetes-from-the-beginning-part-i-4ifd
------

### Team Work ( team player )

100. https://www.atlassian.com/team-playbook/plays/rules-of-engagement

101. https://twist.com/remote-work-guides

102. https://doist.com/blog/lessons-remote-companies/


------

https://itnext.io/building-restful-api-with-node-js-express-js-and-postgresql-the-right-way-b2e718ad1c66

https://techblog.commercetools.com/five-practical-tips-when-using-react-hooks-in-production-990a79745229# 

https://dev.to/koralarts/react-simple-auth-flow-3fbf

https://dev.to/django_stars/best-practices-in-mobile-app-design-in-2020-khn

https://blog.logrocket.com/testing-with-jest-from-zero-to-hero-85ce0e9cc953/

https://patrickheneise.com/2018/01/makefile-for-node-js-developers/

https://medium.com/faun/set-up-a-ci-cd-pipeline-with-kubernetes-minikube-de2bacf7caab

https://docs.aws.amazon.com/sdk-for-javascript/v2/developer-guide/setting-up-node.html

https://aws.amazon.com/es/getting-started/projects/deploy-nodejs-web-app/

https://www.digitalocean.com/community/tutorials/how-to-build-a-node-js-application-with-docker-quickstart?utm_source=digitalocean_newsletter





------
## Learn in Public

https://www.swyx.io/writing/learn-in-public/

Document what you did and the problems you solved.

https://dev.to/swyx/using-dev-to-as-a-cms-3472/

------

* https://gitlab.com/maximilianou/weekly01 ( ecommerce )

* https://gitlab.com/maximilianou/weekly02 ( calendar )

* https://gitlab.com/maximilianou/weekly03 ( analitics )

* https://gitlab.com/maximilianou/weekly04 ( social network )

* https://gitlab.com/maximilianou/weekly05 ( meet ups )

-----
### Side Project

Develop samples and apps. 

 + linux development environment
 + Makefile
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

### Makefile

```
APP=side

all:
	echo "TODO: all"

create:
	docker volume create nodemodules
	express $(APP)_api; cd $(APP)_api; npm i; cd ..;
	npx create-react-app $(APP)_front

start:
	docker-compose up -d

stop:
	docker-compose stop	

list:
	docker-compose ps

clean:
	docker-compose down	
	rm -rf $(APP)_front
	rm -rf $(APP)_api

```
REFERENCE: 

https://gitlab.com/maximilianou/make01


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

https://reactjs.org/docs/hooks-custom.html

```
function todosReducer(state, action) {
  switch (action.type) {
    case 'add':
      return [...state, {
        text: action.text,
        completed: false
      }];
    // ... other actions ...
    default:
      return state;
  }
}
```

```
function useReducer(reducer, initialState) {
  const [state, setState] = useState(initialState);
  function dispatch(action) {
    const nextState = reducer(state, action);
    setState(nextState);
  }
  return [state, dispatch];
}

```

```
function Todos() {
  const [todos, dispatch] = useReducer(todosReducer, []);
  function handleAddClick(text) {
    dispatch({ type: 'add', text });
  }
  // ...
}
```
https://reactjs.org/docs/hooks-reference.html

https://github.com/STRML/react-grid-layout

https://strml.github.io/react-grid-layout/examples/1-basic.html



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

```
curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl
mv kubectl /usr/local/bin
chmod +x /usr/local/bin/kubectl
kubectl version --client
```

```
curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64   && chmod +x minikube
mv minikube /usr/local/bin
```

```
minikube status
minikube start
minikube stop
minikube delete
```

```
kubectl get nodes
```

### aws


-----

