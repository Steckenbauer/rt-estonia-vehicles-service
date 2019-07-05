This is a node js service for currently polling data from:
1. http://transport.tallinn.ee/gps.txt

And pushing it to localhost mqtt broker on port 1883 which is described in Dockerfile.

to build and run:
available --build-arg:
MQTTCLIENTPASS - should be same as mosquitto-server password
OPTURL

docker build -t rt/estonia --build-arg MQTTCLIENTPASS='newPassword' -f Dockerfile .


docker run -d --network="host" rt/estonia 

should be run after mosquitto-server