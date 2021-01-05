# 파이썬의 실행 관련 문제와 해결법 모음

## 파이썬의 설치 경로와 라이브러리의 경로 확인 방법

- 설치는 되어있는데 라이브러리가 import 되지 않을때
- 실행할 때 경로 관련 문제가 발생할 때

#### 파이썬의 설치 경로를 확인하는 방법
```
import sys
print sys.path
```

#### pip에 설치된 라이브러리 목록을 확인하는 방법
```
$ pip list
```

#### 경로를 지정해서 pip로 라이브러리를 설치하는 방법
```
$ pip install --target=_지정경로_ package_name
```
#### --target옵션으로 인스톨할 경우, 기존 파일을 덮어씌우지 않으므로 버전 업그레이드, 덮어씌우기 등을 원할 때에는 --upgrade옵션을 추가해서 실행
```
$ pip install --target=c:\python38\lib\site-packages webdriver_manager --upgrade
```

##### TODO : Selenium과 webdriver_manager의 관계와 사용법
 - [참고 링크](https://stackoverflow.com/questions/55592775/webdriver-manager-start-step-is-getting-stuck-while-executing-in-cmd)