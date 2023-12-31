### 更新Debian存储库信息：
    apt-get update
### 安装NGINX开源软件包：
    apt-get install nginx -y
### 验证安装：
    nginx -v
### 从官方NGINX存储库安装预构建的Debian软件包
#### 安装先决条件
    apt install curl gnupg2 ca-certificates lsb-release debian-archive-keyring
#### 导入官方nginx签名密钥，以便apt可以验证软件包的真实性。获取密钥：
    curl https://nginx.org/keys/nginx_signing.key | gpg --dearmor \
    |  tee /usr/share/keyrings/nginx-archive-keyring.gpg >/dev/null
#### 验证下载的文件是否包含正确的密钥：
    gpg --dry-run --quiet --no-keyring --import --import-options import-show /usr/share/keyrings/nginx-archive-keyring.gpg
#### 输出应包含完整的指纹573BFD6B3D8FBC641079A6ABABF5BD827BD9BF62如下：
    pub   rsa2048 2011-08-19 [SC] [expires: 2024-06-14]
      573BFD6B3D8FBC641079A6ABABF5BD827BD9BF62
    uid                      nginx signing key <signing-key@nginx.com>

如果指纹不同，请删除文件。
### 要为稳定的nginx软件包设置apt存储库，请运行以下命令：
```
echo "deb [signed-by=/usr/share/keyrings/nginx-archive-keyring.gpg] \
http://nginx.org/packages/debian `lsb_release -cs` nginx" \
    |  tee /etc/apt/sources.list.d/nginx.list
```
### 如果您想使用mainlinenginx软件包，请转用以下命令：
```
echo "deb [signed-by=/usr/share/keyrings/nginx-archive-keyring.gpg] \
http://nginx.org/packages/mainline/debian `lsb_release -cs` nginx" \
    |  tee /etc/apt/sources.list.d/nginx.list
```
### 设置存储库固定，以更喜欢我们的软件包而不是分发提供的软件包：
```
echo -e "Package: *\nPin: origin nginx.org\nPin: release o=nginx\nPin-Priority: 900\n" \
    |  tee /etc/apt/preferences.d/99nginx
```
### 安装NGINX软件包：
```
apt update && apt install nginx -y
```
### 启动NGINX开源：
    nginx
### 验证NGINX开源是否已启动并运行：
```
curl -I 127.0.0.1
HTTP/1.1 200 OK
Server: nginx/1.25.1
```
