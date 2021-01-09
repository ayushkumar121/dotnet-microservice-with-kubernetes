# Kubernetes and .NET Microservice test

## Kubernetes

For database
```
    kubectl apply -f .\mongodb.yaml
```

For service
```
    kubectl apply -f .\catalog.yaml 
```

## Docker Commands

```
docker run -d --rm --name mongo -p 27017:27017 -v mongodbdata:/data/da -e MONGO_INITDB_ROOT_USERNAME=mongoadmin -e MONGO_INITDB_ROOT_PASSWORD=Pass#word1 --network=microservices mongo
```

you only need to create mongo to run in development environment

```
docker build -t catalog .

docker run -it --rm --name catalog -p 8080:80 -e MongoDbSettings:Host=mongo -e MongoDbSettings:Password=Pass#word1 --network=microservices ayushkumar121/catalog
```

## Running

launch http://localhost/items