# App-ZNC

## First Time Prerequisites

1. `rm ./Data/example/.gitkeep`

## Running the Containers

1. Edit [znc.conf](./Config/znc.conf) (you can run `docker run -it -v /path/to/znc-cfg:/znc-data znc --makeconf` to generate a new one)
2. Update the following volume mounts in [docker-compose.yml](./Docker/docker-compose.yml)
    * `../Data/znc-data:/znc-data`
    * `../Config/znc.conf:/znc-data/configs/znc.conf`
3. Run `docker run -it -v "/path/to/znc-data":/znc-data znc -p` to generate
   the ssl certificate. Make sure to update `/path/to/znc-data`
4. Run `docker-compose -f ./Docker/docker-compose.yml up -d`

## First Time Setup

1. Visit <https://your-ip:6697> (note, many browsers block port 6697) [This article](https://support.mozilla.org/en-US/questions/1083282) explains how to bypass this restriction in Firefox.
