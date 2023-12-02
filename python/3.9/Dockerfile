# ARG: 환경변수로 지정하여 사용할수 있습니다.
# --build-arg 옵션을 사용하여 빌드 시에 환경 변수를 전달하거나 덮어쓸수 있습니다.
# ex) docker build --build-arg BASE_ALPINE_VERSION=1.11 -t my_image .
# 알파인 리눅스 3.14는 패키지매니저를 통해 3.9버전을 지원합니다.
ARG BASE_ALPINE_VERSION=3.14

# FROM: base로 선택할 이미지, 없으면 remote에서 pull해온다.
FROM alpine:${BASE_ALPINE_VERSION}

ARG PYTHON_VERSION=3

# LABEL: 라벨을 생성하며 docker inspect 커맨드를 통해 label들을 확인 할 수 있다.
LABEL MAINTAINER="tunakim1004@gmail.com"

# RUN: 컨테이너 안에서 명령어를 실행한다. 이미지가 빌드되면서 실행된다.
# 아래 명령어는 python2 버전을 삭제하고 새로 설치된 python3로 유도하는 심볼릭 링크를 생성합니다
# 이를 통해 python 이라 명령해도 python3를 실행시켜 줍니다.
# python 패키지를 실행하는 과정에서 자동으로 실행됩니다.
# ln -sf python3 /usr/bin/python
RUN apk add --update --no-cache python${PYTHON_VERSION}

# CMD: 빌드된 컨테이너가 실행되었을때 실행할 구문을 작성합니다.
CMD ["python3"]
