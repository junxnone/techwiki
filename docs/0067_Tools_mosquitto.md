---
Title | Tools mosquitto
-- | --
Created @ | `2018-11-24T18:39:41Z`
Last Modify @| `2022-12-22T07:20:50Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/67)

---
# Reference
- [mosquitto 官网](http://mosquitto.org/)
- [github repo](https://github.com/eclipse/mosquitto)
- [树莓派安装mqtt服务器](https://blog.csdn.net/ruoyunliufeng/article/details/79174799)

# Brief
- [Install in RPI3B]()
- Build from docker

## Install in RPI 3B

```
wget https://github.com/eclipse/mosquitto/archive/v1.5.4.tar.gz
tar zvxf  v1.5.4.tar.gz
cd mosquitto-1.5.4
sudo apt install cmake g++ libssl-dev libc-ares-dev uuid-dev xsltproc docbook-xsl
mkdir build
cd build
make 
sudo make install
```

Verify | cmd
-- | --
Subscribe | `mosquitto_sub -t test`
Publication | `mosquitto_pub -t test -m 'hello world'`


## Configuration

- 关闭匿名访问

```
 allow_anonymous false
```

- 配置用户和密码文件路径

```
password_file ../build/pwfile.example
```

# UseCase
- work with username&password, Configure the  `allow_anonymous` to false

Usecase | cmd
-- | --
Run Server | `mosquitto -c ~/mosquitto-1.5.4/mosquitto.conf`
Setup the password | `mosquitto_passwd ~/.mosquittopw.conf xxx`
Run a test subscrption | `mosquitto_sub -t test -u username -P userpassword`
Run a test Publication | `mosquitto_pub -t test -u username -P userpassword -m "hello world"`

