Docker-sails
============

This project aims to use Docker containers to run Sails (currently at 0.12.11) and MongoDB with persistence


## How to use
Install Docker and Docker-compose in your machine

Clone the repo and copy the docker folder into your root sails app

Navigate to that folder

Execute
```
docker-compose build
```
Once build, just execute
```
docker-compose up 
```

This will create the containers and run the sails app in console mode. If you need a daemon instead, type
```
docker-compose up -d
```
This setup will also create a MongoDB container with data persistance. In order to use it, you must create the adapter in your connections.js file:
```
MongoAdapter: {
     adapter: 'sails-mongo',
     host: 'mongo',
     port: 27017
   },
```

And then use it in your models.js file:
```
connection: 'MongoAdapter',
```

You are free to use any other database container and create its adapter instead.
