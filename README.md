# hueadm-docker
The docker version of [hueadm](https://github.com/bahamas10/hueadm).

Installation
------------
After setting up docker [docker](https://docs.docker.com/get-docker/), run:

    docker pull mmuffins/hueadm:latest


Usage
------------
#### Invoking Commands
Once the image has been pulled, all functions of the cli are avalable by passing the needed parameters to a new container

    $ docker run --rm mmuffins/hueadm -H 10.0.1.80 -U f28jfl3gtltQw4r4gKLEtVFsfJcBGE87A1RaAXgt lights
    ID  NAME                       STATUS  BRIGHTNESS  REACHABLE
    1   Nightstand                 on      254         true
    2   Garage Right               on      254         false
    ... snipped ...

#### Using a Config File
It is possible to provide a config file by mounting it as volume
    $ vim ~/.hueadm.json
    $ cat ~/.hueadm.json
    {
        "user": "f28jfl3gtltQw4r4gKLEtVFsfJcBGE87A1RaAXgt",
        "host": "10.0.1.80"
    }
    $ docker run --rm --mount type=bind,source=${HOME}/.hueadm.json,target=/hueadm.json mmuffins/hueadm -c /hueadm.json lights
    ID  NAME                       STATUS  BRIGHTNESS  REACHABLE
    1   Nightstand                 on      254         true
    2   Garage Right               on      254         false
    ... snipped ...

#### Using aliases
To simplify the usage of the image, an alias can be set
    $ alias hueadm="docker run --rm -H 10.0.1.80 -U f28jfl3gtltQw4r4gKLEtVFsfJcBGE87A1RaAXgt"
    $ hueadm lights
    ID  NAME                       STATUS  BRIGHTNESS  REACHABLE
    1   Nightstand                 on      254         true
    2   Garage Right               on      254         false
    ... snipped ...

#### Further Examples
For more usage examples and full setup guide see [hueadm](https://github.com/bahamas10/hueadm).