# Ansible-util
#### Ansible 설치
```
yum -y install epel-release
yum -y install ansible git
```

#### SSH Key 생성 및 배포
```
ssh-keygen
ssh-copy-id root@[Node_IP]
```
