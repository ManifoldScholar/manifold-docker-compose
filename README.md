Create and start Manifold containers
```
MANIFOLD_TAG=v3.0.0 docker-compose up -d
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
docker exec -it compose_api_rails_1 \
rails manifold:user:create:admin['email@example.com','test123!','First','Last']
```
