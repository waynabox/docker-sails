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

This Docker Container is based on https://github.com/mcandre/docker-iojs-slim and installs the latest stable version of [Sails.js](http://sailsjs.org/) and is used with the [Sane Stack](https://github.com/artificialio/sane).





You have the docker tags `0.10.35` (fixed versions), `latest` (node 0.11 and latest dependencies), `stable` (node 0.10  and latest dependencies) as well as `0.10.35-pm2`, `latest-pm2` , `stable-pm2` which adds [PM2](https://github.com/Unitech/PM2) to manage your app.

`latest-sails-edge` tracks the canary release candidate for [Sails.js](http://sailsjs.org), currently at [rc4](https://github.com/balderdashy/sails/tree/v0.11.0-rc4), running on node 0.11.