# 说明 （部署前请仔细阅读完）
* Start UP---ADDITIONAL NODE PACKAGES   axios
* 本项目是针对node环境的容器平台和游戏玩具而生，采用nodews组件连接argo隧道部署节点，集成哪吒探针服务(可选)。
* node玩具平台只需上传index.js和package.json即可，需要docker部署的才上传Dockerfile。
* 如需是链接github部署，请先删除README.md说明文件，安全起见，已混淆主代码部分，无日志输出。
* 不填写ARGO_DOMAIN和ARGO_AUTH两个变量即启用临时隧道，反之则使用固定隧道。
* 若遇到已获取到临时隧道但节点不通，说明域名被墙，重启即可
* 哪吒三个变量不全则不运行，无需设置NEZHA_TLS,当哪吒端口为443时，自动开启--tls。
* 右边的Releases中有适配FreeBSD系统的版本，请看清楚对应系统的版本自行下载，像serv00，CT8等

* 容器平台设置的环境变量
  | 变量名        | 是否必须 | 默认值 | 备注 |
  | ------------ | ------ | ------ | ------ |
  | URL          | 否 |       | 项目域名    |
  | UUID         | 否 | 8804add9-5c68-8bab-870c-08cd5320df33|UUID|
  | TIME         | 否 |2 * 60 * 1000|自动访问间隔时间（默认2分钟）
  | NEZHA_SERVER | 否 |        | 哪吒服务端域名，                |
  | NEZHA_PORT   | 否 |  5555  | 当哪吒端口为443时，自动开启tls    |
  | NEZHA_KEY    | 否 |        | 哪吒客务端专用KEY                |
  | ARGO_DOMAIN  | 否 |        | argo固定隧道域名                 |
  | ARGO_AUTH    | 否 |        | argo固定隧道json或token          |
  | CFIP         | 否 |skk.moe | 节点优选域名或ip                 |
  | NAME         | 否 |  Vls   | 节点名称前缀，例如：Glitch，Replit|
  | PORT         | 否 |  3000  |监听端口，也是sub订阅端口          |
  | ARGO_PORT    | 否 |  8001  |ws端口也是argo隧道端口，使用固定隧道token请改回8080，或在cf后台更改端口与这里对应 |

# 节点信息
* 本项目采用ws连接argo隧道，输出list和sub文件和sub订阅，，域名/sub查看节点信息，list文件在2分钟后会自动删除。
* 节点订阅：项目分配的域名/sub  例如：https://www.google.com/sub
* 非标端口订阅（游戏类）：项目分配的域名:端口/sub  例如：http://www.google.com:1234/sub

# 其他
* 右边的package是本项目的镜像，支持镜像部署的推荐使用镜像，本项目已添加自动访问保活功能，需在index.js第10行中添加项目分配的域名。可配合外部保活，项目地址：https://github.com/eoovve/Auto-keep-online
  
# 免责声明
* 本程序仅供学习了解, 非盈利目的，请于下载后 24 小时内删除, 不得用作任何商业用途, 文字、数据及图片均有所属版权, 如转载须注明来源。
* 使用本程序必循遵守部署免责声明，使用本程序必循遵守部署服务器所在地、所在国家和用户所在国家的法律法规, 程序作者不对使用者任何不当行为负责。

