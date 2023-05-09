---
title: Grub Rescue 해결법
author: Hajun
date: 2023-05-09 23:30:00 +0900
categories: [linux, solution]
tags: [linux, grub, rescue, dualbooting, windows]
---

Desktop에 리눅스와 윈도우를 같이 쓰고 있었는데, 어느날 부팅하자마자 이런 메세지가 떴다.

```
error: no such partition.
Entering rescue mode... 
grub rescue>
```
왜 이런 증상이 생겼지에 대한 이유도 사실 모르겠지만, 일단 당장 해야하는게 있어 해결방법부터 찾아보았다.

1. ls 를 치면 (hd0) (hd0,msdos1)  (hd0,msdos2) ....  이렇게 나온다.
2. 이제 어떤 파티션이 리눅스가 설치되어 있는지 찾아봐야한다.
3. ls (hd0,msdos1), ls (hd0,msdos2) ... 하면서 각각 찾아보자.
```
error: unknown filesystem         #이게 나오면 여긴 아니다.
(hd0,msdos5):filesystem is ext2   #이게 나오면 여기다.
```
4. 그렇다면 이제 어디 파티션인지 알았다면 다음과 같이 입력한다.
```
set prefix=(hd0,msdos5)/boot/grub   #필자는 (hd0,msdos5)에 있었다.
insmod normal
normal
```

5. 이러면 grub을 살렸지만 아직 반만 된것이다. 재부팅하면 동일한 증상이 나타난다.
6. 리눅스로 들어가서 터미널에 다음과 같이 입력하면 최종적으로 완료가 된다.
```
sudo update-grub
sudo grub-install /dev/sda
```

이후, 원인을 찾아보니 다음과 같은 이슈 때문이라고 한다.
1. 파티션 or 부트로더 파일이 삭제되거나 손상된 경우
2. 하드드라이브 실패, 파티션 크기 조정 중 실패, 부트로더가 다른 운영 체제의 설치로 덮어쓰기 되었을 경우



