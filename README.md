# crontab-manager
crontab-manager 是一套对linux下crontab的管理系统，主要提供crontab界面化的管理，即管理多台crontab服务。<br />
### 主要功能点
1、提供对任务的增，删，改，查，手动触发执行，暂停，启用，并确保任务不会重复执行。<br />
2、提供任务执行记录，执行结果，执行状态，执行耗时。<br />
3、提供查看远程主机任务列表，任务执行失败报警等功能。<br />
### 工作原理
crontab-manager系统是前后端分离的，crontab-frontend使用Vue.js, crontab-backend使用php提供接口<br />
所以下图用户可以直接调接口，也可通过页面操作<br />
![avatar](https://github.com/kaiyuan-finance/crontab-manager/blob/master/Arch.png)

### 安装
首先准备一台任务机，就是执行crontab的机器，如果想一键安装就让任务机开放出来一个ssh的用户，用来连接任务机初始化环境。<br />
一键安装：<br>
```bash
./install.sh 11.11.11.11:9099 11.11.11.22:8088 "devops:123456@11.11.11.33:2222"
```
第一个参数是后端接口对外提供访问的地址，端口必填。<br />
第二个参数是前端页面对外提供访问的地址，端口必填。<br />
第三个参数是任务机的地址，这个参数的作用主要有2个：1初始化crontab-backend的ansible调用环境，2.初始化任务机crontab的ssh认证环境。<br />
如果这个任务机地址不对外提供ssh登录时，则只初始化crontab-backend的ansible调用环境，而crontab的ssh认证环境需要手动的去初始化。<br />
如果不提供这个参数则，crontab-backend的ansible，crontab的ssh认证环境 都需要自己手动初始化。<br />

只安装crontab-backend服务：<br />
```bash
./install.sh 11.11.11.11:9099 "devops:123456@11.11.11.33:2222"
```
第一个参数对应上面 ./install.sh的第一个参数，作用一样<br />
第二个参数对应上面 ./install.sh的第三个参数，作用一样<br />

只安装crontab-frontend服务：<br />
```bash
./install.sh 11.11.11.11:9099 11.11.11.22:8088
```
第一个参数对应上面 ./install.sh的第一个参数，作用一样<br />
第二个参数对应上面 ./install.sh的第二个参数，作用一样<br />
