# golang-jwt

# Endpoints
```
POST /register
POST /login
GET /profile
```

`/profile` защищен.
Сначала необходимо отправить запрос на `/register`, тело которого содержит данные пользователя:
```json
{
    "email": "johndoe@mail.com",
    "name": "John",
    "password": "password"
}
```
Затем необходимо отправить запрос на `/login`, тело которого содержит email и пароль
```
{
    "email": "johndoe@mail.com",
    "password": "password"
}
```

Вернется bearer токен, с которым отправляем запрос на `/profile` и получаем информацию о профиле пользователя
```json
{
    "email": "johndoe@mail.com",
    "name": "John"
}
```

# Docker

## Готовый

```
docker run -p 8080:8080 lapindanil22/golang-jwt
```

## Или вручную

```
docker build -t golang-jwt .
docker run --name=golang-jwt -p 8080:8080 golang-jwt
```
