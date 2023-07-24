# Ansible 을 사용하여 CEPH 클러스터 구성 시 필요한 요소들 설치
***CentOS 7.9***
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

#### Ansible 설정 변경 및 Playbook 실행
- inventory와 hosts에 IP 정보 기입 후 사용
```
vi inventory
vi hosts
ansible-playbook -i inventory ceph_pre-install.yaml
```

#### 시간 동기화
```
ln -sf /usr/share/zoneinfo/Asia/Seoul /etc/localtime
```
