## 새로 HDD 추가하여 리눅스 /home 디렉리 확장하기

* 새로 추가한 HDD정보 확인한다
```sh
sudo fdisk -l
```
	(py3) hkh@nlpgpu4:~/sources$ fdisk -l
	Disk /dev/sda: 953.9 GiB, 1024209543168 bytes, 2000409264 sectors
	Units: sectors of 1 * 512 = 512 bytes
	Sector size (logical/physical): 512 bytes / 512 bytes
	I/O size (minimum/optimal): 512 bytes / 512 bytes
	Disklabel type: dos
	Disk identifier: 0xc8ad06d9

	Device     Boot      Start        End    Sectors  Size Id Type
	/dev/sda1  *          2048 1866346495 1866344448  890G 83 Linux
	/dev/sda2       1866348542 2000408575  134060034 63.9G  5 Extended
	/dev/sda5       1866348544 2000408575  134060032 63.9G 82 Linux swap / Solaris


	Disk /dev/sdb: 3.7 TiB, 4000787030016 bytes, 7814037168 sectors
	Units: sectors of 1 * 512 = 512 bytes
	Sector size (logical/physical): 512 bytes / 4096 bytes
	I/O size (minimum/optimal): 4096 bytes / 4096 bytes

HDD의 장치명이 `/dev/sdb` 임을 알 수 있다.

* mk2efs 명령으로 파일 시스템 생성한다
```sh
mke2fs -t ext4 /dev/sdb
```

* HDD 장치를 시스템 파일시스템으로 마운트한다
```sh
mount /dev/sdb /mnt
```

* 기존 `/home` 디텍터리 모든 파일을 `/mnt` 디텍터리로 복사한다.
```sh
rsync -avP /home/ /mnt/
```

* root 계정으로 로그인하여 기존 파일시스템의 `/home` 디텍터리를 지운다!

**_주의: 모든 파일이 지워지므로 반드시 백업이 잘 되었는지 확인하고 진행한다!_**
```sh
rm -r /home
```

* 부팅시 마운트 포인트를 `/home`으로 지정한다
```sh
vim /etc/fstab
```

```sh
# 파일 마지막에 다음 라인 추가
# mount hard disk to /home
UUID=bf87d6cb-e641-4736-addc-0b6e94104a97 /home ext4    rw,relatime,acl 0       2
```

```sh
# UUID 확인방법
ll /dev/disk/by-uuid
```

* 재부팅하면 HDD는 `/home` 디렉터리로 마운트된다
```
  Filesystem      Size  Used Avail Use% Mounted on
  udev             63G     0   63G   0% /dev
  tmpfs            13G  9.4M   13G   1% /run
  /dev/nvme0n1p2  332G   17G  299G   6% /
  tmpfs            63G     0   63G   0% /dev/shm
  tmpfs           5.0M  4.0K  5.0M   1% /run/lock
  tmpfs            63G     0   63G   0% /sys/fs/cgroup
  /dev/sdb        5.5T  285G  4.9T   6% /home
  /dev/nvme0n1p1  511M  3.5M  508M   1% /boot/efi
  tmpfs            13G     0   13G   0% /run/user/1001
```
