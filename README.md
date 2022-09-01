# Push-a-Docker-Image-to-AWS-ECR
A quick tutorial on how to push a Docker image to AWS Elastic Container Registry 

First things first, create an account on docker hub https://hub.docker.com/

Then download and install Docker desktop for whichever operating system you are using
you can now check if it was installed correctly with the `docker --version command`

<img width="351" alt="Screen Shot 2022-08-29 at 2 56 03 PM" src="https://user-images.githubusercontent.com/9061503/187276890-ac0182b8-c272-4bc9-8170-e02f19d188a4.png">

Next we must use the `docker login` commad to log into our docker account, you should get a message saying **login succeeded**


Now NANO create a file named **Dockerfile** and paste the following:

`FROM node:12.17.0`

`WORKDIR /app`

`COPY package*.json ./`

`RUN npm install`

`COPY . .`

`ENV PORT=3000`

`EXPOSE 3000`

`CMD [ "npm", "start" ]`

# Now we can run a Docker build command
`docker build -t <name-tag>`

You may name this anything you want: **make sure you have docker running or you will get an error**
-
You should see something like this when your image is being created.

<img width="562" alt="Screen Shot 2022-08-29 at 3 48 15 PM" src="https://user-images.githubusercontent.com/9061503/187286499-3cbfabca-6a97-46d4-9217-14724c0a43cc.png">

