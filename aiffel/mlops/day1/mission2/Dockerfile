# <<EOF 쓰는 이유

FROM --platform=$BUILDPLATFORM python:3.10-alpine AS builder

WORKDIR /code

COPY requirements.txt /code
RUN --mount=type=cache,target=/root/.cache/pip pip3 install -r requirements.txt

COPY . /code

# ENTRYPOINT ["python3"]
# CMD ["app.py"]

ENTRYPOINT [ "python3", "app.py" ]

# ------------------------------------------------
# ------------------------------------------------

FROM builder as dev-envs

RUN apk update
RUN apk add git bash

RUN <<EOF
addgroup -S docker
adduser -S --shell /bin/bash --ingroup docker vscode
EOF

# install Docker tools (cli, buildx, compose)
COPY --from=gloursdocker/docker / /
