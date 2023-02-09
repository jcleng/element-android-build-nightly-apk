# element-android-build-nightly-apk
build nightly apk for https://github.com/vector-im/element-android

- 生成签名文件

```shell
D:\work\zulu11.56.19-ca-jdk11.0.15-win_x64\bin\keytool.exe -genkey -v -keystore signkey.jks -storetype JKS -keyalg RSA -keysize 2048 -validity 10000 -alias element123
# 输入2次密码 element123
# 保存signkey.jks文件到项目根目录
```
