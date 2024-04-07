# rain.dex.solve

This repo composes various options for solving Raindex. By design there are no
implementations in this repo

## Docker compose

Pruning orphans is useful if we accidentally modify the compose file while
containers are still running.
E.g. if we git pull before pulling them down.

Start:

```
docker compose up -d --remove-orphans
```

Stop

```
docker compose down
```


## Docker volumes

This docker compose uses external volumes so they have to be created manually.

```
volume_path=/absolute/path
volume_name=foo-volume
docker volume create --driver local --opt type=none --opt device="$volume_path" --opt o=bind $volume_name
```