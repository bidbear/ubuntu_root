# Ubuntu18.4配置root用户

打开终端
进入临时root账户  `sudo -s`

执行：`sudo passwd root`   修改root账户的密码（红色的下划线表示空格，这个命令很简单不会用请自行百度）

打开文件"/etc/pam.d/gdm-autologin"将这个文件中的"auth    required    pam_succeed_if.so user != root quiet_success"注释掉后保存。

打开文件"/etc/pam.d/gdm-password"将这个文件中的"auth    required    pam_succeed_if.so user != root quiet_success"注释掉后保存。

打开文件"/root/.profile"将这个文件的最后一行修改为"tty -s && mesg n || true"

重启电脑

在登录时选择未列出，用户名写root，密码是之前修改的root账户的密码，这样就可以用root账户登录了

