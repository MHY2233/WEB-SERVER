#### 安装acme.sh
    curl https://get.acme.sh | sh -s email=my@example.com

#### 生成证书
    acme.sh --issue -d 你的域名 --standalone -k ec-256 --force

#### 安装证书
    acme.sh --installcert -d 你的域名 --fullchainpath /root/fullchain.crt --keypath /root/private.key --ecc --force

#### 手动更新证书
    acme.sh/acme.sh --renew -d 你的域名 --force --ecc

#### 更新 acme.sh
```bash
手动升级 acme.sh 到最新版 `acme.sh --upgrade`

自动更新 acme.sh 到最新版 `acme.sh --upgrade --auto-upgrade`
```
