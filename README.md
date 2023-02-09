# element-android-build-nightly-apk
build nightly apk for https://github.com/vector-im/element-android


使用`element-android`的`nightly`版本进行构建
自定义了默认的`matrix`和`matrix.to`服务器地址(action可以选择)
使得在国内能直接使用(`matrix.org`国内访问不了)
签名用的本项目的签名

- [关于通知和推送支持了unifiedpush](https://github.com/vector-im/element-android/blob/develop/docs/unifiedpush.md)

```shell
# gplay(nightly就是)默认是用的google服务(国内无法使用,导致不能收到推送)
# F-Droid使用的是后台轮询(理论来说比较费电)

# 然后提供了unifiedpush服务: https://unifiedpush.org/users/distributors/ntfy/
# 安装ntfy,打开会自动注册默认的(统一推送)
# 最后再element里面设置通知,选择ntfy即可(需要把ntfy和element都设置自启和通知权限)
```

- 生成签名文件

```shell
D:\work\zulu11.56.19-ca-jdk11.0.15-win_x64\bin\keytool.exe -genkey -v -keystore signkey.jks -storetype JKS -keyalg RSA -keysize 2048 -validity 10000 -alias element123
# 输入2次密码 element123
# 保存signkey.jks文件到项目根目录
```

- pc版本,配置自己的地址

```shell
flatpak install flathub im.riot.Riot -y
# 编辑配置文件 https://github.com/vector-im/element-web/blob/develop/docs/config.md
/home/jcleng/.var/app/im.riot.Riot/config/Element/config.json
# 配置自己的服务器地址如下
{
    "default_server_config": {
       "m.homeserver": {
          "base_url": "https://matrix.leng2011.icu"
       }
    }
 }

```
