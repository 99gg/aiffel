```sh
# 이미지 가져오기
docker pull python:3.10-slim

# 이미지 목록 보기
docker images

# 컨테이너 실행하기
docker run -it python:3.10-slim
# Python 3.10.14 (main, Jul 23 2024, 07:20:18) [GCC 12.2.0] on linux
# Type "help", "copyright", "credits" or "license" for more information.
# >>>

# 컨테이너 중지하기
docker stop $container_id

# 컨테이너 삭제하기
docker rm $container_id

# 이미지 삭제하기
docker rmi python:3.10-slim
```

```sh
docker build -t $image_name:$tag_name .
docker run -d --name $your_container_name $your_image_name:$tag_name
```
