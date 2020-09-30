```bash
git clone https://github.com/Invoice-build/app-dev.git invoice-build && cd invoice-build
```

```bash
git submodule init && git submodule update
```

```bash
docker-compose run api rails db:create
docker-compose run api rails rake seed:tokens
```

```bash
docker-compose up
```
