同時に複数起動する場合は  
Vagrantfile  
に記載されている
```
config.vm.network "private_network", ip: "192.168.33.10"
```
の値を適宜変更する  
ローカルマシンの/etc/hostsの内容も適宜変更する  
