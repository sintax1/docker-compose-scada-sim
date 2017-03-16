# SCADA/ICS Simulator
This is a docker compose configuration for running a SCADA simulated environment.

## Running the Scada Simulator

1. Install Docker + Docker Compose

    [Install Instructions](https://docs.docker.com/compose/install/)

2. Build & Run the containers
```bash
[docker host]$ git clone https://github.com/sintax1/docker-compose-scada-sim.git
[docker host]$ cd docker-compose-scada-sim
[docker host]$ docker-compose up
```

3. Login to the Mango HMI
```
http://[docker host IP]:8080/login.htm

username: admin
password: admin
```

4. Load a configuration into the HMI
```
http://[docker host IP]:8080/emport.shtm
```

[Water Plant config](https://github.com/sintax1/mango-automation-configs/blob/master/config.json)

5. View the dashboard

    [Water Plant Dashboard](http://172.16.201.129:8080/dashboards/waterplant)

## Notes
### Capture the scada traffic by sniffing on docker 'scada-ot-1' network instarface
```bash
[docker host]$ tcpdump -i br-$(docker network ls --filter "name=.*scada-ot-1" --format "{{.ID}}")
```
