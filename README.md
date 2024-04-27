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

      # Install Pipeline Stage View, Gitlab, Maven, and Docker plugins.
      # Create Gitlab settings and authentication token.
      docker exec -it -u root jenkins bash
      apt install maven
### hosts

      # Add 127.0.0.1 gitlab.example.com
      # Add 127.0.0.1 jenkins.example.com

### docker-compose.yml

      services:
        jenkins:
          container_name: jenkins
          image: jenkins/jenkins:latest 
          hostname: jenkins.example.com
          ports:
            - "8080:8080"
          volumes:
            - $PWD/jenkins_home:/var/jenkins_home
          networks:
            - net 
            
        gitlab:
          container_name: gitlab
          image: 'gitlab/gitlab-ce:latest'
          hostname: gitlab.example.com
          ports:
            - '80:80'
          volumes:
            - $PWD/gitlab_home/config:/etc/gitlab
            - $PWD/gitlab_home/logs:/var/log/gitlab
            - $PWD/gitlab_home/data:/var/opt/gitlab
          networks:
            - net
      networks:
        net:

          # volumes:
          #  - '/srv/gitlab/config:/etc/gitlab'
          #  - '/srv/gitlab/logs:/var/log/gitlab'
          #  - '/srv/gitlab/data:/var/opt/gitlab'

### Jenkins pipeline

      node {
          APP_NAME = 'order-service-test'
          RELEASE = '1.0.0'
          
          stage("Cleanup Workspace"){
              cleanWs()
          }
          stage("Checkout from SCM"){
              git branch: 'main', url: 'http://gitlab/root/order-service-test.git'
          }
          stage("Test") {
              //sh "mvn test"
          }
          stage("Build") {
              sh "mvn -DskipTests package"
          }
      }
          
      
