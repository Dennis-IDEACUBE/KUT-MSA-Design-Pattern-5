# KUT-MSA-Design-Pattern-5

http://naver.me/G6frYiaU

### VirtualBox 

      VBoxManage natnetwork add --netname NatNetwork --network "192.168.15.0/24" --enable --dhcp off --port-forward-4 "ssh:tcp:[]:22:[192.168.15.101]:22"
      VBoxManage natnetwork --port-forward-4 "ssh:tcp:[]:23:[192.168.15.102]:22"
      
      VBoxManage setextradata global GUI/Input/HostKeyCombination 162,164
