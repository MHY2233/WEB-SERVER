### apt update && apt -y install socat 

### 安装acme.sh
    curl https://get.acme.sh | sh -s email=my@example.com

### 安装成功后执行 source ~/.bashrc 以确保脚本所设置的命令别名生效。

### 使用acme.sh获取签发证书.
    acme.sh --issue -d 你的域名 --standalone -k ec-256 --force

### 安装证书到/root
    acme.sh --installcert -d 你的域名 --fullchainpath /root/fullchain.crt --keypath /root/private.key --ecc --force

### 手动更新证书
    ~/.acme.sh/acme.sh --renew -d 你的域名 --force --ecc