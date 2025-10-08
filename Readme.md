git: Tutorial

1. git --version
1. git config --global user.name "github name"
1. git config --global user.email "your email"

1. git init
1. git add .
1. git commit -m "your-command"

1. git branch -M main
1. git remote add origin repo_url
1. git push -u origin main

1. git push
1. git pull     or git remote update
1. git fetch
1. git status
1. git log      or git log -p    #press Q to quite
1. git diff
1. git rebase branch-name  #to transfer completed work to branch-name

1. git merge branch-name  #to merge current branch to branch-name
1. git push    #after you merge

1. git status
1. git branch                                                            #to list all branches
1. git branch branch-name                                     #to create new one

1. git checkout branch-name       #to switch to any branch/ to navigate
1. git checkout -b branch-name  #to create fearture-branch
1. git branch -d branch-name  #to delete

1. git clone urls
1. git remote add origin urls


Docker tutorial

1. docker --version               #check version of the docker
1. docker run hello-world     #pull an image
1. docker ps -a                      #list all containers
1. docker ps                          #show info of the running container
1. docker stop container1 container2 container3
1. docker rm container_id     #remove
1. docker rmi nginx               #remove nginx image
1. docker rmi -f nginx           #remove docker container prune
1. docker rmi nginx hello-world  #remove two images or more

1. docker build -t mern-backend .    #build an image
1. docker run -p 5000:5000 --name backend --env-file .env mern-backend

1. docker build -t mern-frontend .    #build an image
1. docker run -p 5173:5173 --name frontend --env-file .env mern-frontend

Config: Dockerfile 

FROM node:20-alpine

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

RUN npm run build

EXPOSE 5173     #5000 for backend

CMD [ "npm", "start"]

Docker compose: Tutorial
Docker-compose.yml       It is created in the root.
```js
services:
   backend:
      build: ./server
      container_name: backend
      restart: always
      env_file:
         -  ./server/.env
      port:
         - "5000:5000"

    frontend:
       build: ./client
       container_name: frontend
       restart: always
       ports:
          - "5173:5173"
       depends_on:
         - backend

```
Notes: Docker-compose.yml is a Tool to manage multiple container apps.

1. docker-compose up --build
1. docker-compose up --build -d
1. docker-compose down
1. docker-compose logs
1. docker-compose logs backend
1. docker-compose logs frontend