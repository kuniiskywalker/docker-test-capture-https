# generate server.key and server.crt
```
$ openssl genrsa 2048 > server.key
$ openssl req -new -key server.key > server.csr
$ openssl x509 -days 3650 -req -signkey server.key < server.csr > server.crt
```

# docker image build
```
docker-compose build
```

# docker container run 
```
docker-compose up -d
```

# capture packet

output to data directory

```
docker-compose exec https tcpdump -Z root -i eth0 -s 0 -w dump_https.pcap port 443
```
