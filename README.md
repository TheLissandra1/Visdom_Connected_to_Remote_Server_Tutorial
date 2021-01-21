# Visdom_Connected_to_Remote_Server_Tutorial
This is the tutorial of how to connect VISDOM  locally when training in a remote server (GPU)~
## 1st step: find a local host number: 4301/6942? 在本地的cmd中输入 ssh -L 18097:127.0.0.1:8097 nq001@138.37.37.237, 输入密码登录
## 2nd step: 在远程服务器中启动visdom，在浏览器中访问127.0.0.1:18097

注2：如果你不能直接访问服务器ip，可以用ssh开个隧道。本地cmd终端输入ssh nq001@138.37.37.237 -L 127.0.0.1:8888:127.0.0.1:8097
然后浏览器打开138.37.37.237:8888就行了
