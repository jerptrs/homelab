1. openssl genrsa -out mosquitto-ca.key 2048
2. openssl req -new -x509 -days365 -key mosquitto-ca.key -out mosquitto-ca.crt
3. openssl genrsa -out mosquitto-serv.key 2048
4. openssl req -new -key mosquitto-serv.key -out mosquitto-serv.csr
5. openssl x509 -req -in mosquitto-serv.csr -CA mosquitto-ca.crt -CAkey mosquitto-ca.key -CAcreateserial -out mosquitto-serv.crt -days 365 -sha256

move certs to /usr/share/container/mosquitto/certs