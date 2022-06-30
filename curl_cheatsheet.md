# Curl Cheatsheet

## GET

Print content of url to terminal
```shell
curl https://api.chucknorris.io/jokes/random
```

download content of url to file
```shell
curl https://api.chucknorris.io/jokes/random -o randomjoke.txt
```

## POST

```shell
curl -i -H "Accept:application/json" \
        -H "Content-Type:application/json" \
        -H "Authorization: Bearer ACCESS-TOKEN" \
        -XPOST "https://gorest.co.in/public/v2/users" \
        -d '{"name":"Tenali Ramakrishna", \
             "gender":"male", "email":"tenali.ramakrishna@15ce.com", \
             "status":"active"}'
```