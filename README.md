# KUT-MSA-Design-Pattern-5

http://naver.me/G6frYiaU

### VirtualBox 

      VBoxManage natnetwork add --netname NatNetwork --network "192.168.15.0/24" --enable --dhcp off --port-forward-4 "ssh:tcp:[]:22:[192.168.15.101]:22"
      VBoxManage natnetwork --port-forward-4 "ssh:tcp:[]:23:[192.168.15.102]:22"
      
      VBoxManage setextradata global GUI/Input/HostKeyCombination 162,164

### Visual Studio Code Extensions

      code --install-extension MS-CEINTL.vscode-language-pack-ko
      code --install-extension ms-vscode-remote.remote-ssh
      code --install-extension ms-azuretools.vscode-docker
      code --install-extension vscjava.vscode-java-pack
      code --install-extension vscjava.vscode-gradle
      code --install-extension vmware.vscode-boot-dev-pack

      copy id_rsa on Host Windows(C:\Users\사용자\.ssh)

      -- config --------------------------------------
      Host labserver
      HostName localhost
      Port 22101
      User user1
      IdentityFile C:\Users\사용자\.ssh\id_rsa
      ------------------------------------------------

### Git 

      git config user.name "dennis"
      git config user.email "itgenius1004@gmail.com"

      git remote -v
      git push --force myapp-test

      git config credential.helper store
      git config credential.helper store --global

      git config credential.helper store
      git config --global --unset credential.helper

### GitLab

      # Disable the default branch protected property in Gitlab
      # Generated GitLab root's Personal Access Tokens

### Jenkins

      # Install Gitlab, Maven, and Docker plugins.
      # Create Gitlab settings and authentication token.
      
