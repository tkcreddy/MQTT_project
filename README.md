# MQTT_project
http://www.steves-internet-guide.com/mosquitto-tls/ --- Reference


1. sudo passwd root
2. sudo apt-get install mosquitto
3. sudo apt-get install mosquitto-client
4. sudo apt install python
5. sudo apt-get update
6. sudo apt-get install python-setuptools python-dev build-essential

openssl genrsa -des3 -out ca.key 2048

openssl req -new -x509 -days 1826 -extensions v3_ca -keyout ca.key -out ca.crt

openssl genrsa -out server.key 2048

openssl req -out server.csr -key server.key -new

openssl x509 -req -in server.csr -CA ca.crt -CAkey ca.key -CAcreateserial -out server.crt -days 365

sudo cp ca.crt /etc/mosquitto/ca_certificates/

sudo cp server.crt server.key /etc/mosquitto/certs/
