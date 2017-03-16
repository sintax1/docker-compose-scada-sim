# docker-compose-scada-sim

## Running the Scada Simulator

1. Install Docker + Docker Compose

    [Install Instructions](https://docs.docker.com/compose/install/)

2. Build & Run the containers
```bash
[docker host]$ git clone https://github.com/sintax1/docker-compose-scada-sim.git
[docker host]$ cd docker-compose-scada-sim
[docker host]$ docker-compose run < docker-compose.yml
```
3. Load the configuration into Mango HMI
    [Mango Config](https://github.com/sintax1/mango-automation-configs/blob/master/config.json)


## Notes:
- Capture the scada traffic by sniffing on docker 'scada-ot-1' network instarface
```bash
[docker host]$ tcpdump -i br-$(docker network ls --filter "name=.*scada-ot-1" --format "{{.ID}}")
```
