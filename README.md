# Using InterSystems IRIS Community Edition with Kong Community Edition

Notes on using the two together.  Examples all in containers.

https://docs.konghq.com/gateway/latest/install/docker/

## just-kong

This directory just shows how to start Kong CE with docker-compose.  It's a very light edit of what's provided by Kong to enable the management portal.  You can read more about it here:

https://docs.konghq.com/gateway/latest/install/docker/

* Kong's externally facing data plane is exposed on localhost:8000
* Kong's management console is exposed on localhost:8002

## kong-and-iris

This directory builds off `just-kong` and adds the IRIS Community Edition to the docker-compose file.  This file 

1. Create a service to `http://iris:52773/api/monitor`
2. Create a route to the service you created above
3. Try it out: `curl http://localhost:8000/monitor/metrics`

* IRIS's management portal is exposed on localhost:9000
* IRIS's superserver is exposed on localhost:9001

