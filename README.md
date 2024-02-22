![dwhack](https://github.com/Cloud-Hacks/movie-catalogue-gravitee/assets/11625672/6e38bccd-2cf1-4d0b-bf66-e6fe536ca601)

Movie Catalogue API is an application programming interface (API) leveraged by Gravitee APIM that provides functionality to manage and retrieve information about movies in a movie catalog. It serves as a backend service that allows developers to interact with the movie database, perform CRUD (Create, Read, Update, Delete) operations, and search for movies based on various criteria.


### Setup

- Requirements
```
Golang v1.17+, Docker, Kubernetes, Helm Chart
```
- Either Run the API locally or push your own docker image and modify the helm chart

`make run`

OR

`make docker-start`

## Post a movie

```
curl -X POST http://localhost:8081/movie -H 'Content-Type: application/json' -d '{
    "title": "Avatar III",
    "year": 2024,
    "cast": ["Sam Worthington"],
    "genres": ["Action"]
}'
```

## Retrieve a movie by year

```
curl localhost:8081/movies/year/2021
```

```
curl --header "X-Gravitee-Api-Key: YOUR_API_KEY" \
https://trial.apim.trial-devex.gravitee.xyz/movies/year/10
```

## Retrieve a movie by name

```
curl localhost:8081/movies/name/Av
```

## To generate server

```
oapi-codegen -package main -generate 'types,server,spec' swagger.yaml > server.gen.go
```
