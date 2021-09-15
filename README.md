# HowToUse-magiskssh

# 安卓配置ssh服务端的笔记

下载并安装我上传至git上的magisk模块（感谢作者，在一片无人区又为了实现一个奇葩需求的程序猿开辟了一条路）

随便找个能生成ssh密钥的Linux用一下 ssh-keygen （用xshell貌似也是可以的）

获得生成的私钥id_rsa和公钥id_rsa.pub

cd到.ssh目录 当时版本的.ssh目录为 /data/ssh/root/.ssh或者 /data/ssh/shell/.ssh（我还没弄清楚为什么会有两个目录，难道一个是shell一个是root？）

cd /data/ssh/root/.ssh

用文件管理器把生成的公钥id_rsa.pub丢到/data/ssh/root/.ssh目录里面来安装公钥

cat id_rsa.pub >> authorized_keys

设置权限

chmod 600 authorized_keys

我到这一步ssh服务端就已经弄好了，可以测试一下。

## 还有部分操作 如果发现出现问题可以修改修改看看

设置权限：chmod 700 ~/.ssh

修改sshd_config文件 ：

RSAAuthentication yes 

PubkeyAuthentication yes
