unzip binary.zip

chmod +x gfw2udp_amd64 speeder_amd64

mv gfw2udp_amd64 speeder_amd64 /usr/local/bin



ip=``curl ifconfig.me``

sed -r 's/(\b[0-9]{1,3}\.){3}[0-9]{1,3}\b'/"$ip"/g speederServer.service

sed -r 's/(\b[0-9]{1,3}\.){3}[0-9]{1,3}\b'/"$ip"/g gfw2udpServer.service

sed -r s/8443/69/g speederServer.service

sed -r s/8443/69/g gfw2udpServer.service

Server

systemctl enable speederServer.service

systemctl start speederServer.service

systemctl status speederServer.service

systemctl enable gfw2udpServer.service

systemctl start gfw2udpServer.service

systemctl status gfw2udpServer.service

Client

systemctl enable speederClient.service

systemctl start speederClient.service

systemctl status speederClient.service

systemctl enable gfw2udpClient.service

systemctl start gfw2udpClient.service

systemctl status gfw2udpClient.service

