---
title: "Purescript環境構築用Dockerfile"
date: 2021-03-22T00:28:01+09:00
draft: false
---

purescriptの環境構築に苦戦することが多いためDockerfileを作成しました.
ビルドすればpurs(コンパイラ)とspago(ビルドツール)が使える状態になっています.
Dockerfileの中でaptを使うのは非推奨らしく,今後できれば対応したいです.

この記事の執筆時点でのDockerfileを下記に示しますが,更新は
**[Dockerfileの置いてあるGithubリポジトリ yutaro-sakamoto/purescript-spago](https://github.com/yutaro-sakamoto/purescript-dockerfile)**
に対してだけ反映するつもりです.

```dockerfile
FROM ubuntu:20.04
LABEL maintainer="yutaro-sakamoto@yutaro-sakamoto.com"

RUN apt update -y
RUN apt upgrade -y
RUN apt install -y tzdata
RUN apt install -y nodejs npm git libncurses5

# install psvm
RUN npm install -g psvm

# install purs
RUN psvm install v0.14.0
RUN psvm use v0.14.0
RUN echo 'export PATH="$PATH:/root/.psvm/current/bin/"' >> ~/.bashrc

# install spago
RUN npm install -g spago

ENTRYPOINT ["/bin/bash"]
```
