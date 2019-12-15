# README

## Tutorials Mixed together : 

- Docker for Rails Developers
- Effective Testing with **RSpec 3**
- Agile Development with **Rails 5.1**


# Getting started 

From branch *start/docker_rails*

## Creating Rails app

```
docker-compose run --rm web bundle install
```

* Change owner of created files
```
chown -R $USER:$USER .
```

## Configuring Database
* Create and set environment variables folder
```
mkdir -p .env/development/
```
* Set those variables 
```
POSTGRES_USER=postgres
POSTGRES_PASSWORD=password_db
POSTGRES_DB=my_app_development
```


## Spinning up the Rails app
```
docker-compose up -d 
```
