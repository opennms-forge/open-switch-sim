# OpenNMS Switch Simulator project

This project simulates an **SNMP agent** for sending traps and managing snmpwalk requests. It can be deployed using Docker. There are following components:

- Switch Simulator UI (web client)
- Mock SNMP agent (Spring Boot)

Docker image is published to [Docker Hub](https://hub.docker.com/r/opennms/switch-sim/)

You can run it:
```console
$ docker run -e OPENNMSSERVER_ADDRESS='123.123.123.123' -e OPENNMSSERVER_AGENTPORT=161 -e OPENNMSSERVER_CARDS=4 -e OPENNMSSERVER_PORTS=8 -p 8080:8080  -t opennms/switch-sim
```
*Notes:*

OPENNMSSERVER_CARDS specifies a number of switch cards on SNMP agent

OPENNMSSERVER_PORTS specifies a number of ports **per** card

Set OPENNMSSERVER_ADDRESS argument to your OpenNMS server host ip

## Accessing

- To access **CONSOLE** (Switch Simulator UI for SpringBoot GateWay) for switch simulator: `http://localhost:8080/console.html`

- SpringBoot **GateWay** for managing switch sim requests: `http://localhost:8080/switchcontroller/?status=1&port=1`

*Notes:*
status: 1 is up, 2 is down
