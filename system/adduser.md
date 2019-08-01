> 在centos 系统下创建具有root权限的用户

```
useradd zhanghx  # 添加zhanghx 的用户
passwd zhanghx  # 为zhanghx 用户创建密码(在提示框中输入)
vim /etc/sudoers # 修改sudo 配置文件
```
在 `root	ALL=(ALL) 	ALL` 下面添加语句`zhanghx	ALL=(ALL) 	ALL `   语句

修改完毕，用zhanghx帐号登录，然后用命令**su–**，即可获得root权限进行操作。

使用`sudo -s`可以变更为root 账户权限
  
