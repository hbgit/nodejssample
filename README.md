# nodejssample

# Install docker-compose

First of all install docker.

Now install compose, based on https://docs.docker.com/compose/install/

1) sudo curl -L "https://github.com/docker/compose/releases/download/1.23.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

2) sudo chmod +x /usr/local/bin/docker-compose

3) Test the installation.
    $ docker-compose --version

Note: If the command docker-compose fails after installation, check your path. You can also create a symbolic link to /usr/bin or any other directory in your path.

sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose


# Starting app

1) sudo docker-compose up

# Testing post request
2) curl -H "Content-Type: application/json" -d '{"marca":"ferrari", "modelo":812 }' -X POST http://localhost:9000/api/carros/novo

# Checking the database
3) http://localhost:9000/api/carros

# Testing CRUD
Insert
4) curl -H "Content-Type: application/json" -d '{"marca":"Nissan", "modelo":"March" }' -X POST http://localhost:9000/api/carros/novo

[{"_id":"5c98f77d3946cf0074eaf7f9","marca":"Nissan","modelo":"March","creadoEm":"2019-03-25T15:45:01.908Z","__v":0}]

Update
5) curl -H "Content-Type: application/json" -d '{"marca":"Nissan", "modelo":"March 1.6" }' -X "PUT" http://localhost:9000/api/carros/editar/5c98f77d3946cf0074eaf7f9

Delete
6) curl -H "Content-Type: application/json" -d '{"marca":"Nissan", "modelo":"March 1.6" }' -X "DELETE" http://localhost:9000/api/carros/delete/5c98f77d3946cf0074eaf7f9
