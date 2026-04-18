# fastfrps

FRP server image with Web UI enabled.

## Run

```bash
docker run -d \
  --name fastfrps \
  --restart always \
  --network host \
  -e TOKEN=your-token \
  -e DASHBOARD_USER=admin \
  -e DASHBOARD_PWD=strong-password \
  -e DASHBOARD_PORT=7898 \
  your-dockerhub-user/fastfrps:latest
```

Open `http://your-server-ip:7898`.

## Env

- `TOKEN` required
- `DASHBOARD_USER` default `admin`
- `DASHBOARD_PWD` default `change_me`
- `DASHBOARD_PORT` default `7898`
- `MAX_POOL_COUNT` default `5`

## Notes

- FRP bind port stays `7000`
- Client and server `TOKEN` must match

## Build

```bash
docker buildx build --platform linux/arm64,linux/amd64 -t your-dockerhub-user/fastfrps:latest -f Dockerfile.fastfrps --push .
```

MIT
