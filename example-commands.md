# running a network discovery
docker run -u root --rm -v ${PWD}:/opt/orb/ -e DIODE_API_KEY netboxlabs/orb-agent:develop run -c /opt/orb/network.yaml

# running a device discoery
docker run -u root --rm -v ${PWD}:/opt/orb/ -e DIODE_API_KEY netboxlabs/orb-agent:develop run -c /opt/orb/device.yaml

# running from git policy
docker run -u root --rm -v ${PWD}:/opt/orb/ -e DIODE_API_KEY netboxlabs/orb-agent:develop run -c /opt/orb/git.yaml

# running a custom worker
docker run -u root --rm -v ${PWD}:/opt/orb/ -e DIODE_API_KEY -e INSTALL_DRIVERS_PATH=/opt/orb/workers.txt netboxlabs/orb-agent:develop run -c /opt/orb/worker.yaml

# running the MIST worker
docker run -u root --rm -v ${PWD}:/opt/orb/ -e DIODE_API_KEY -e MIST_APITOKEN -e MIST_ORG_ID -e INSTALL_DRIVERS_PATH=/opt/orb/workers.txt netboxlabs/orb-agent:develop run -c /opt/orb/worker.yaml
