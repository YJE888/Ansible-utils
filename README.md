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

#### ansible을 사용하여 ping 테스트
```
ansible -i inventory all -m ping
```

## error
ansible을 실행했을 때 이와 같은 에러가 발생했을 때 `fatal: [gpu]: FAILED! => {"ansible_facts": {"discovered_interpreter_python": "/usr/bin/python"}, "changed": false, "msg": "Failed to import the required Python library (Docker SDK for Python: docker (Python >= 2.7) or docker-py (Python 2.6)) on gpu's Python /usr/bin/python. Please read module documentation and install in the appropriate location. If the required library is installed, but Ansible is using the wrong Python interpreter, please consult the documentation on ansible_python_interpreter, for example via pip install docker or pip install docker-py (Python 2.6). The error was: No module named requests.exceptions"}` pip로 도커 설치
```
pip install docker
```

***pip install docker***를 실행했을 때 이와 같은 에러가 발생한다면 `Command "python setup.py egg_info" failed with error code 1 in /tmp/pip-build-rXdXdJ/requests/
You are using pip version 8.1.2, however version 22.2.2 is available.
You should consider upgrading via the 'pip install --upgrade pip' command.` 업그레이드 진행 후 재시도
```
pip install --upgrade pip==20.3
pip install --upgrade pip
```
