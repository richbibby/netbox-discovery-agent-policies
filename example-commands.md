# Commands to Start Orb Agents for NetBox Discovery

## Network Discovery Agent (agent01)
```
docker run -u root --rm \
  -v ${PWD}:/opt/orb/ \
  -e DIODE_API_KEY \
  netboxlabs/orb-agent:develop run -c /opt/orb/network-discovery.yaml
```

## Device Discovery Agent (agent02)
```
docker run -u root --rm \
  -v ${PWD}:/opt/orb/ \
  -e DIODE_API_KEY \
  -e SSH_USERNAME \
  -e SSH_PASSWORD \
  netboxlabs/orb-agent:develop run -c /opt/orb/device-discovery.yaml
```

## Custom Worker Discovery Agent (agent03)
```
docker run -u root --rm -v ${PWD}:/opt/orb/ -e DIODE_API_KEY -e INSTALL_DRIVERS_PATH=/opt/orb/workers.txt netboxlabs/orb-agent:develop run -c /opt/orb/worker-discovery.yaml
```