# crontab-manager
crontab-manager 是一套对linux下crontab的管理系统，主要提供crontab界面化的管理，即管理多台crontab服务。<br />
### 主要功能点
1、提供对任务的增，删，改，查，手动触发执行，暂停，启用，并确保任务不会重复执行。<br />
2、提供任务执行记录，执行结果，执行状态，执行耗时。<br />
3、提供查看远程主机任务列表，任务执行失败报警等功能。<br />
### 工作原理
![avatar](https://github.com/kaiyuan-finance/crontab-manager/blob/master/Arch.png)

### 安装
首先准备一台任务机，就是执行crontab的机器，如果想一键安装就让任务机开放出来一个ssh的用户，用来连接任务机初始化环境。<br />
一键安装：<br>
```bash
./install.sh 172.16.68.36:9099 172.16.68.36:8088 "devops:123456@172.16.68.36:2222"
```

