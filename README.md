# Visdom Connected to Remote Server Tutorial
This is the tutorial of how to connect VISDOM  locally when training in a remote server (GPU)~
#### 1st step:
 - login remote QM server through <username> e.g. nq001
 - 登录远程QM服务器
#### 2nd step: 
 - In local cmd window, enter  ```ssh -L 18097:127.0.0.1:8097 nq001@138.37.37.237 ``` , enter password to login, 127.0.0.1 is local ip and 138.37.37.237 is QM Server's ip, which is checked by cmd command 'netstat -ano', 8097 is the default port number for visdom, 18097 is the local port number.
 - 在本地的cmd中输入 ssh -L 18097:127.0.0.1:8097 nq001@138.37.37.237, 输入密码登录, 注意不能出现 permission denied字样
#### 3rd step: 
 - module load anaconda3-->source activate Nishacondaenv-->python -m visdom.server, then visit 127.0.0.1:18097 in local browser, you do not have to access to dupin/fortunato/usher/prospero GPUs in this step
 - 加载anaconda模块和环境，在远程服务器中启动visdom，在本地浏览器中访问127.0.0.1:18097
#### 4th step:
  - open a duplicate session in Pageant (PuTTY), login to QM remote server, then access to any GPU Servers (dupin/fortunato/usher/prospero), dupin/fortunato/usher/prospero, load anaconda and environment, run your python file directly.
  - 在Pageant中开一个duplicate session, 登录QM远程服务器，接入GPU，加载anaconda模块和环境，直接运行想要可视化的python文件
  - In EnglightenGAN training process: 
   ```python
    python scripts/script.py --train
   ```
 * <img src = "https://raw.githubusercontent.com/TheLissandra1/Visdom_Connected_to_Remote_Server_Tutorial/main/Images/visdom.png" width="100%">
#### tips:
* If "OSError: [Errno 98] Address already in use",
    - use 'netstat -tunlp' to show ongoing processes,
    - then use 'kill -9 <process number>' to kill python process
* If "Connection Error" occurs,
    - Restart your computer/laptop!
* If 'RuntimeError: CUDA error: out of memory',
    - Use 'nvidia-smi' to check available memory.
* 查看Linux GPU使用情况
    - nvidia-smi
