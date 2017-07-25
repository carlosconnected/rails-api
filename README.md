# Demo

## Curl command examples

```
curl -H "Content-Type: application/json" -d '{ "auth":{"email": "luke@starwars.com","password": "12345678"}}' https://carlos-rails-api.herokuapp.com/user_token

curl https://carlos-rails-api.herokuapp.com/users
```

## Client app example

https://next-with-api-wbykqnmlyl.now.sh/

# Get Started

1. Install [rails](https://gorails.com/setup/ubuntu/16.04)
2. Install [postgresql](https://www.postgresql.org/download/)
3. Then:

```
git clone git@github.com:carlos-peru/rails-api.git
cd rails-api
rails db:migrate
rails s
```

# Users field

Field | Description
------|------------
**id** | The item's unique id.
name | The user's name. Required.
email | The user's email. Required.
password | At least 8 characters. Required.

# Authentication

## Request
```
POST /user_token
{"auth": {"email": "USER_EMAIL", "password": "USER_PASSWORD"}}
```

## Response
```
201 Created
{"jwt": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9"}
```

# User API

## All users

```
GET /users
```

## Current user

```
Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9

GET /users/current
```

## Show user

```
Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9

GET /users/USER_ID
```

## Create user

```
Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9
Content-Type: application/json

POST /users
{"user":{"name":"USER_NAME","email":"USER_EMAIL","password": "USER_PASSWORD","password_confirmation":"USER_PASSWORD"}}
```
