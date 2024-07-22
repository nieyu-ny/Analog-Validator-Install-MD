# Analog-Validator-Install-MD
1、检查是否安装docker
  
  docker --version
  
  未安装则执行docker安装命令：
  
  curl -fsSL https://get.docker.com | bash -s docker
  
2、使用官方docker镜像安装Analog，将节点名称修改为自定义名称后执行即可
  
  docker run -d --network="host" --name analog -v /var/lib/analog:/data analoglabs/timechain \
  --base-path /data \
  --rpc-external \
  --unsafe-rpc-external \
  --rpc-cors all \
  --name=这里是节点名称，改为你自己想设置的名字 \
  --rpc-methods Unsafe
  
3、安装完成后通过docker命令查看运行情况
  docker ps -a

![image](https://github.com/user-attachments/assets/cedf25b8-b990-4f0e-b7e7-e07230da9661)

4、执行命令获取会话密钥，后续领取测试网代币时使用

  curl http://127.0.0.1:9944 -H \
  "Content-Type:application/json;charset=utf-8" -d \
    '{
      "jsonrpc":"2.0",
      "id":1,
      "method":"author_rotateKeys",
      "params": []
    }'
    
    运行结果中，result的值就是会话密钥

![image](https://github.com/user-attachments/assets/940857a3-dcff-4ec0-8972-26e3edabcd13)


5、创建钱包

  1）添加Talisman钱包插件(钱包插件地址:https://chromewebstore.google.com/detail/talisman-ethereum-and-pol/fijngjgcjhjmmpcmkeiomlglpeiijkld?pli=1)
  
  2）创建Polkadot钱包账号
  ![image](https://github.com/user-attachments/assets/22e66f8a-7853-4dff-987e-790460b1fc52)
  
  3）获取钱包地址
  
  选择钱包账号
  
  ![image](https://github.com/user-attachments/assets/06b8a7af-8a2e-4b75-a5b6-b1701c9e9b43)
  
  选择网络Analog Testnet，复制账号地址
  
  ![image](https://github.com/user-attachments/assets/e30318d6-7f2c-4c04-9769-9b6533402d6a)
  
6、加入官方Discard群，领取测试网代币
官方DIscard群链接：https://discord.com/invite/analog
找到faucet频道，发送【!faucet 第五步获取的钱包地址】领取测试网代币
![image](https://github.com/user-attachments/assets/b33c1b36-d674-4317-baa8-c1ce35b27c34)

7、前往官方网站https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Frpc.testnet.analog.one#/explorer绑定验证器、钱包及会话地址
1）使用第五步创建的钱包连接到测试网
![image](https://github.com/user-attachments/assets/a520a110-1953-45c4-9b8d-e637d0debc52)
2）选择网络-质押-账户-设置验证人
![image](https://github.com/user-attachments/assets/f0f8aad0-b6ad-40e0-b3db-66fc26f5edf3)
3）绑定第六步领取了测试网代币的钱包
![1b5b5ddfb269898d6c0b36a799c8999](https://github.com/user-attachments/assets/2ad9ac20-142c-4220-be6b-0fb7c9615bd6)
4）绑定会话密钥（第四步获取的）
![b0ce4deeaf5ddfb372ed4fb6132a48f](https://github.com/user-attachments/assets/9ff0e5ea-610d-4920-9f61-96e4f4428626)
5）绑定成功后等待验证者上链即可，可通过官网查看节点同步
https://telemetry.analog.one/#/0x0614f7b74a2e47f7c8d8e2a5335be84bdde9402a43f5decdec03200a87c8b943
![image](https://github.com/user-attachments/assets/b21a7d23-7833-42b9-8f98-7619293ec0a7)



