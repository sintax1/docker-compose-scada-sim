# SCADA/ICS Simulator
This is a docker compose configuration for running a SCADA simulated environment.

## Running the Scada Simulator

1. Install Docker + Docker Compose

    [Install Instructions](https://docs.docker.com/compose/install/)

2. Build & Run the containers
```bash
[docker host]$ git clone https://github.com/sintax1/docker-compose-scadasim.git
[docker host]$ cd docker-compose-scadasim
[docker host]$ docker-compose up
```

3. Login to the Mango HMI
```
http://[docker host IP]:8080/login.htm

username: admin
password: admin
```

4. Load a configuration into the HMI, or build your own through Mango

     [Water Plant config](https://github.com/sintax1/mango-automation-configs/blob/master/config.json)

```
http://[docker host IP]:8080/dashboards/settings/import-export
```

5. View the dashboard
```
    http://[docker host IP]:8080/dashboards/waterplant
```

## Notes
### Capture the scada (Modbus/TCP) traffic by sniffing on docker 'scada-ot-1' network interface
```bash
[docker host]$ tcpdump -i br-$(docker network ls --filter "name=.*scada-ot-1" --format "{{.ID}}")
```
