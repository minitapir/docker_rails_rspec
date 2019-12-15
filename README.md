# README

## Tutorials Mixed together : 

- Docker for Rails Developers
- Effective Testing with **RSpec 3**
- Agile Development with **Rails 5.1**


# Getting started 

From branch *start/docker_rails* :

## Creating Rails app

* Get gems from **Gemfile** :
```
docker-compose run --rm web bundle install
```

* Create app with **postgresql** as database and without *tests* (**-T**), without *git* (**-G**) and without executing *bundle install* (**-B**):
```
docker-compose run --rm bin/rails new -TGB -d postgresql 
``` 

* Change owner of created files :
```
chown -R $USER:$USER .
```

## Setting up RSpec

* In **Gemfile** :

```ruby
gem 'rspec-rails', '~> 3.8'
```

* Then, from a Rails container :

```
docker-compose run --rm web bin/rails generate rspec:install
```

## Configuring Database
* Create and set environment variables folder (**.env**)
```
mkdir -p .env/development/
```
* Set those variables 
```
POSTGRES_USER=postgres
POSTGRES_PASSWORD=password_db
POSTGRES_DB=my_app_development
```

* Create the databases needed :
```
docker-compose run --rm web bin/rails db:create
```

## Spinning up the Rails app
```
docker-compose up -d 
```
