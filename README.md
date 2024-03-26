# run-pgm-on-cmd

注：完成后请不要关闭终端，不然会结束进程！

要在Windows的cmd中安装Chocolatey，可以按照以下步骤进行：

1. 打开一个管理员权限的cmd窗口。
2. 执行以下命令来下载并运行Chocolatey的安装脚本：

```cmd
@"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"
```

3. 安装完成后，关闭当前cmd窗口并重新打开一个新的管理员权限的cmd窗口。
4. 现在你可以使用Chocolatey来安装软件了。你可以使用以下命令来安装git：

```cmd
choco install git -y
```

拉取项目至 ```desktop```目录。(当然这里可以更改)：

sudo -i
cd /desktop && git clone https://github.com/TeamPGM/PagerMaid-Pyro.git pgp && cd pgp


随后使用choco安装python3
 打开 cmd 窗口（以管理员身份运行），然后执行以下命令：

```bash
choco upgrade all -y  # 更新 Chocolatey 自身和所有已安装的软件包
choco install python3 -y  # 安装 Python3
choco install imagemagick -y  # 安装 ImageMagick
choco install neofetch -y  # 安装 Neofetch
choco install tesseract --version 5.0.0-alpha.20201127 -y  # 安装 Tesseract OCR（注意：这里安装的是 Tesseract 5 的预览版本）
```
安装软件包过程中，请等待一段时间，安装完成后，继续进行以下操作。
安装 Python 后，`pip` 和 `venv` 应该已经包含在其中了，你可以通过以下命令验证：

```bash
python -m pip --version  # 检查 pip 是否安装成功
python -m venv --version  # 检查 venv 是否安装成功
```


首先启用虚拟环境：


```cmd
python -m venv venv
venv\Scripts\activate
```
可以看到命令行前面多了一个 (venv) ，即表示启用成功。

```cmd
copy config.gen.yml config.yml
```

修改 config.yml：

```cmd
Vim config.yml
```

若不会使用vim编辑器请自行学习

若Windows本地没有vim编辑器可以输入一下命令：

```cmd
choco install vim
```

修改配置文件中的api_id和api_hash即可

日志及报错信息记录 (可选) ：

```
log: "False"    # False 代表禁用，True 代表启用
log_chatid: "503691334"    # 这里填写记录用的群组或频道ID
```

代理 (可选) ：

```
proxy_addr: ""    # socks5 代理地址
proxy_port: ""    # socks5 代理端口
http_addr: ""    # http 代理地址
http_port: ""    # http 代理端口
mtp_addr: ""    # mtp 代理地址
mtp_port: ""    # mtp 代理端口
mtp_secret: ""    # mtp 代理密钥
```

二维码登录 (可选) ：

```
qrcode_login: "False"    # False 代表禁用，True 代表启用
```

登录账号 请确保仍在虚拟环境中，即有 (venv) 标志，然后运行以下命令：

```
python3 -m pagermaid
```

此步需要填入完整的电话号码 (eg：+18888888888，需要带上国际区号) 然后 Telegram 会向你的其他客户端发送验证码，少数用户会向手机号发送验证码，填入验证码后，回车，如有两步验证密码，则再输入两步验证密码即可。

```
Enter phone number or bot token:    #此处填入手机号
Is "+18888888888" correct? (y/N):    # 号码显示正确输入 y ,错误输入 n
The confirmation code has been sent via Telegram app
Enter confirmation code:    # 此处输入 Telegram APP 中收到的验证码
# 如果设置了两步验证，则会出现以下提示
The two-step verification is enabled and a password is required
Password hint: None
Enter password (empty to recover):    # 此处输入两步验证密码
```

注：完成后请不要关闭终端，不然会结束进程！
