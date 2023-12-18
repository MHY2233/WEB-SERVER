# 稳定版本：
#### 1.
    apt install -y debian-keyring debian-archive-keyring apt-transport-https
#### 2.
    curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/gpg.key' |  gpg --dearmor -o /usr/share/keyrings/caddy-stable-archive-keyring.gpg
#### 3.
    curl -1sLf 'https://dl.cloudsmith.io/public/caddy/stable/debian.deb.txt' |  tee /etc/apt/sources.list.d/caddy-stable.list
#### 4.
    apt update
#### 5.
    apt install caddy
# 测试版本（包括 beta 和候选版本）：
#### 1.
    apt install -y debian-keyring debian-archive-keyring apt-transport-https
#### 2.
    curl -1sLf 'https://dl.cloudsmith.io/public/caddy/testing/gpg.key' |  gpg --dearmor -o /usr/share/keyrings/caddy-testing-archive-keyring.gpg
#### 3.
    curl -1sLf 'https://dl.cloudsmith.io/public/caddy/testing/debian.deb.txt' |  tee /etc/apt/sources.list.d/caddy-testing.list
#### 4.
    apt update
#### 5.
    apt install caddy