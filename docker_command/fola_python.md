```shell
docker run \
-i -t \
--name fola_python \
--hostname fola_pyton \
-v ~/docker_volume/fola_python_home:/home \
python:3.9 \
/bin/bash
```