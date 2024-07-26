# <<EOF 쓰는 이유
# entrypoint, cmd차이
# entrypoint, cmd 같이 쓰는 이유
# COPY 2번 나눠서 하는 이유

FROM --platform=$BUILDPLATFORM python:3.10-alpine AS builder

WORKDIR /code

COPY requirements.txt /code
RUN --mount=type=cache,target=/root/.cache/pip \
  pip3 install -r requirements.txt

COPY . /code

ENTRYPOINT ["python3"]
CMD ["app.py"]

# ------------------------------------------------
# ------------------------------------------------

FROM builder as dev-envs

# RUN <<EOF
# apk update
# apk add git
# apk add bash
# EOF

RUN apk update
RUN apk add git
RUN apk add bash

RUN <<EOF
addgroup -S docker
adduser -S --shell /bin/bash --ingroup docker vscode
EOF
# install Docker tools (cli, buildx, compose)
COPY --from=gloursdocker/docker / /
