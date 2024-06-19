## Ansible로 서버 초기 설정

#### CentOS 7.9
- Ansible playbook 실행 시 다음과 같은 에러가 난다면 호스트키 검사를 비활성화 하거나, 호스트 키를 자동 업데이트 하는 방법을 설정 가능
```
fatal: [xxx.xxx.xxx.xx]: FAILED! => {"msg": "Using a SSH password instead of a key is not possible because Host Key checking is enabled and sshpass does not support this.  Please add this host's fingerprint to your known_hosts file to manage this host."}

# 비활성화 방법
- name: Linux Settings
  hosts: all

  vars: # Playbook에 내용 추가
    ansible_ssh_common_args: '-o StrictHostKeyChecking=no -o UserKnownHostsFile=/dev/null' # Playbook에 내용 추가
  tasks:
...
```
