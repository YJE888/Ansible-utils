# ANSIBLE 확인
#### ansible로 시간 설정 후 모든 노드에 확인하는 명령어
```
ansible -i inventory -m shell -a "date" all
```
