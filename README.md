# CyberDog_Ctrl
[![chn](https://img.shields.io/badge/lang-chn-green.svg)](https://github.com/Karlsx/CyberDog_Ctrl/blob/main/README.md)
This project implements the [gRPC](http://doc.oschina.net/grpc?t=58008) client by which sending commands to Cyberdog. The communicate protocol is official open source[cyberdog_app.proto](https://partner-gitlab.mioffice.cn/cyberdog/athena_cyberdog/-/tree/devel/athena_common/athena_grpc/protos), since there is no specific protocol description document, we can only predict the use method of the specific interface based on the application mode on the mobile App.
Currently, only basic movement control and basic action command control are available.

### Dependencies

- grpc：      `sudo pip install grpcio`
- grpc-tools：`sudo pip install grpcio-tools`
- keyboard：  `sudo pip install keyboard`

### Protocol generation

Download protocol file：[cyberdog_app.proto](https://partner-gitlab.mioffice.cn/cyberdog/athena_cyberdog/-/tree/devel/athena_common/athena_grpc/protos) and save it in the same directory as `make_proto.bash`, run `make_proto.bash`
Then `cyberdog_app_pb2.py` and `cyberdog_app_pb2_grpc.py` files will be generated.

### gRPC Protocol
The demo is implemented by python，and gRPC supports c++，c#，Go，Java，Node，php，ruby，objective-c

Official document : [GitHub](https://github.com/grpc/grpc)


### How to use
Connect Cyberdog to the network using the official CyberdogApp, using the Jetson NX module as a PC or via USB cable + SSH.
Get Cyberdog's IP address by shell cmd `ifconfig` in Cyberdog's terminal. Connect your PC to the same network.
Run ：`sudo python3 cyberdog_ctrl.py`
Input mode-selected and IP:
- RunOrderCMD：
  The following actions are performed：
  - Stand up
  - Shake hands
  - Get down

- RunMoveCMD：
  The following actions are performed：
  - Stand up
  - Swith gait to slow tort
  - Move  base command
  - Get down
