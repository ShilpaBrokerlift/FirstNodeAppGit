
#Using the LST version of node
FROM node:8

#Creating directory
WORKDIR /usr/src/app

#Install all dependency from package and package-lock
COPY package*.json ./

RUN npm install

#Bundle app source code
COPY . .

#App binds to port 3000 so expose the docker to this port
EXPOSE 3000

#Runtime: Command to run the app through CMD, runs the file 
#defined in 'main' under pakcage.json
CMD [ "npm","start" ]
