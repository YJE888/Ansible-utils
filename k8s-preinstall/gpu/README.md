# GPU 노드에서 gpu-preinstall 이후 확인해야될 사항
#### 그래픽카드 모델명 확인 [PCIe]
```
# yum -y install pciutils
lspci -k | grep -EA2 'VGA|3D'
```

## 리눅스 내장그래픽(nouveau) 비활성화 [재부팅 필요]
*nouveau는 오픈 소스 그래픽 드라이버로 NVIDIA 그래픽 카드를 위한 드라이버이지만, NVIDIA가 제공하는 공식 드라이버를 사용할 것이므로 비활성화*
- nouveau 사용 확인(결과값이 확인되면 사용 중)
```
lsmod | grep nouveau
```
- nouveau 비활성화
```
cat <<EOF > /etc/modprobe.d/blacklist.conf
blacklist nouveau
option nouveau modeset=0
EOF

```
- 블랙리스트 설정 적용을 위한 initramfs 업데이트 후 재부팅
```
dracut --force
reboot
```
