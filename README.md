# docker-mongo-replica-set


## SETUP

- RUN `docker-compose build`
- RUN `docker-compose up -d`
- OPEN MAIN MONGO INSIDE DOCKER BY RUNNING `docker exec -it mongo1 mongo`
- OPEN PRIMARY MONGO INSIDE DOCKER BY RUNNING `docker exec -it mongo1 mongo`
- RUN 
```javascript
    config = {
      "_id" : "my-mongo-set",
      "members" : [
        {
          "_id" : 0,
          "host" : "mongo1:27017"
        },
        {
          "_id" : 1,
          "host" : "mongo2:27017"
        },
        {
          "_id" : 2,
          "host" : "mongo3:27017"
        }
      ]
      };
```
- RUN `rs.initiate(config);`


## INFO
- connection string to primary `mongodb://localhost:30001/?directConnection=true`

## TODO
- Automate replica primary/secondary integration setup
