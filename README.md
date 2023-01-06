# docker-systemd

This repository contain Docker images with systemd.

## Build

```console
docker build --ulimit nofile=1024:262144 -t opstty/systemd:<os>-<version> <os>/<version>/.
docker push opstty/systemd:<os>-<version>
```

## Usage

```console
docker run -d --name <container-name> --tmpfs /tmp --tmpfs /run --privileged --cgroupns=host --volume=/sys/fs/cgroup:/sys/fs/cgroup:rw opstty/systemd:<os>-<version>
docker exec -ti <container-name> /bin/bash
docker rm -f <container-name>
```

## License

MIT / BSD

## Author Information

This repository was created in 2023 by [Michael HATOUM](mailto:michael@opstty.com)
