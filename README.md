[Noctifer-Music](https://github.com/lrkrol/Noctifer-Music) in a Docker image.

# Build & Run using `docker-compose`

Set your configuration in the [.env](.env) file:
- `LOCAL_MUSIC_DIR`: path to the directory that contains all your audio files
- `LOCAL_PORT`: port to expose this web server. Use `127.0.0.1:<PORT>` for local-only.

Example:
```
LOCAL_MUSIC_DIR=/home/vanolucas/Music
LOCAL_PORT=8080
```

Then run `docker-compose` in this directory containing [docker-compose.yml](docker-compose.yml):
```bash
docker-compose up --build -d
```

Browse to the container's URL. e.g. [http://localhost:8080/](http://localhost:8080/).

# Use Noctifer-Music

Default password: `123`.

See [Noctifer-Music github repo](https://github.com/lrkrol/Noctifer-Music) for more detail.

# Stop

```bash
docker-compose down
```