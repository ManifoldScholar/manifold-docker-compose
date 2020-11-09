Before spinning up the containers, modify `environment/manifold.env` so that it contains the correct IP or domain name for your server. You'll need to replace 127.0.0.1 from the following env vars:

```
DOMAIN=127.0.0.1:4000
CLIENT_BROWSER_API_URL=http://127.0.0.1:4000
CLIENT_BROWSER_API_CABLE_URL=http://127.0.0.1:4000/cable
```

Create and start Manifold containers
```
MANIFOLD_TAG=v5.1.4-beta.1 docker-compose up -d
```

Access the site in your browser. Might take a minute for services to start.
```
http://127.0.0.1:4000
```

Tail container log output (ctrl + c to stop)
```
docker-compose logs -f
```

Restart Manifold containers
```
docker-compose restart
```

Stop Manifold containers
```
docker-compose stop
```

Stop and remove Manifold containers
```
docker-compose down
```

Access the Rails (Manifold API Backend) console
```
docker exec -it compose_api_rails_1 rails c
```

Create an admin user
```
docker exec -it manifold-docker-compose_api_rails_1 \
rails manifold:user:create:admin['email@example.com','test123!','First','Last']
```
