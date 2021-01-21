# Visdom_Connected_to_Remote_Server_Tutorial
This is the tutorial of how to connect VISDOM  locally when training in a remote server (GPU)~
#### 1st step:
> login remote QM server through nq001
> 登录远程服务器
#### 2nd step: 
> In local cmd window, enter 'ssh -L 18097:127.0.0.1:8097 nq001@138.37.37.237', enter password to login
> 在本地的cmd中输入 ssh -L 18097:127.0.0.1:8097 nq001@138.37.37.237, 输入密码登录, 注意不能出现 permission denied字样
#### 3rd step: 
> module load anaconda3-->source activate Nishacondaenv-->python -m visdom.server, then visit 127.0.0.1:18097 in local browser
> 加载anaconda模块和环境，在远程服务器中启动visdom，在本地浏览器中访问127.0.0.1:18097


#### tips:
* If "OSError: [Errno 98] Address already in use",
    - use 'netstat -tunlp' to show ongoing processes,
    - then use 'kill -9 <process number>' to kill python process
