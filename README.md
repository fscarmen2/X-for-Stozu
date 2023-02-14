# Argo Xray for Stozu.net

* * *

# 目录

- [项目特点](README.md#项目特点)
- [部署](README.md#部署)
- [鸣谢下列作者的文章和项目](README.md#鸣谢下列作者的文章和项目)
- [免责声明](README.md#免责声明)

* * *

## 项目特点:
* 本项目用于在 [Stozu.net](https://panel.stozu.net/) 免费服务上部署 Xray
* 根据本平台自行修改的哪吒探针，以能使用其 VNC 达到 ssh 的效果，可以自由选择是否安装
* 使用 CloudFlare 的 Argo 隧道，直接优选 + 隧道，CDN 不用再做 workers
* 针对本项目另辟蹊径处理 root 权限，可玩性大大增加
* 部署完成如发现不能上网，请检查域名是否被墙，可使用 Cloudflare CDN 或者 worker 解决。参照文章：https://www.hicairo.com/post/57.html
* 前端 js 定时保活，会玩的用户可以根据具体情况修改间隔时间
* 节点信息以 V2rayN / Clash / 小火箭 链接方式输出

## 部署:
* 注册 [Stozu.net](https://panel.stozu.net/)
* entrypoint.sh 的 6-8 行修改 UUID、WS 路径和哪吒变量
* PaaS 平台用到的变量
  | 变量名        | 是否必须 | 默认值 | 备注 |
  | ------------ | ------ | ------ | ------ |
  | UUID         | 否 | de04add9-5c68-8bab-950c-08cd5320df18 | 可在线生成 https://www.zxgj.cn/g/uuid |
  | WSPATH       | 否 | argo | 勿以 / 开头，各协议路径为 `/WSPATH-协议`，如 `/argo-vless`,`/argo-vmess`,`/argo-trojan`,`/argo-shadowsocks` |
  | NEZHA_SERVER | 否 |        | 哪吒探针服务端的 IP 或域名 |
  | NEZHA_PORT   | 否 |        | 哪吒探针服务端的端口 |
  | NEZHA_KEY    | 否 |        | 哪吒探针客户端专用 Key |

* 需要应用的 js
  | 命令 | 说明 |
  | ---- |------ |
  | <URL>/list | 查看节点数据 |
  | <URL>/listen | 查看后台监听端口 |
  | <URL>/root | 开启 root，需要手动，以后入系统输入`root`即可进入 root 模式 |

<img width="1565" alt="image" src="https://user-images.githubusercontent.com/62703343/216829709-47729bf2-1f6a-446b-bd7a-c8f51b87333d.png">

<img width="1268" alt="image" src="https://user-images.githubusercontent.com/92626977/218685807-aad027fa-7822-4eac-9626-b9891c123f2f.png">

<img width="1623" alt="image" src="https://user-images.githubusercontent.com/62703343/216830025-ede5ed09-9c5b-460d-b0ef-26435b08cc5e.png">

<img width="1655" alt="image" src="https://user-images.githubusercontent.com/62703343/216871461-f2f0c75f-ccd3-429e-bc35-c0ebae978f07.png">

<img width="1358" alt="image" src="https://user-images.githubusercontent.com/62703343/216830682-c7e94f5c-118b-46bc-a5c3-e662c1f023f2.png">

<img width="1678" alt="image" src="https://user-images.githubusercontent.com/62703343/216872742-a58648b0-97bd-478c-a539-cbeb198fb4b6.png">

<img width="1499" alt="image" src="https://user-images.githubusercontent.com/62703343/216831263-06d73f8d-d09f-4933-ac31-00e9e8315013.png">

<img width="1614" alt="image" src="https://user-images.githubusercontent.com/62703343/216831034-25b39a58-6a30-40a1-9dfd-8c3083e666fa.png">

<img width="1524" alt="image" src="https://user-images.githubusercontent.com/62703343/216831178-e1c6262f-4e75-4282-bc1c-2185e3c30ee8.png">

<img width="1198" alt="image" src="https://user-images.githubusercontent.com/92626977/212642206-6b12179d-b35a-4a1e-b4e1-963b537c7693.png">

<img width="1198" alt="image" src="https://user-images.githubusercontent.com/92626977/212642268-d72bdaf0-a9df-4727-b8d4-fc8b360ee507.png">

<img width="1198" alt="image" src="https://user-images.githubusercontent.com/92626977/213434139-252d8226-e29e-4c16-93d8-ec1ca8439a25.png">

<img width="793" alt="image" src="https://user-images.githubusercontent.com/62703343/216873357-65266d9d-181a-461e-b487-446b347b4b9e.png">
  
<img width="513" alt="image" src="https://user-images.githubusercontent.com/62703343/216873498-eea1bd03-58e0-4cb1-9b06-b61ac3bc6083.png">

## 鸣谢下列作者的文章和项目:
* 大佬 Nike Jeff 的项目文件
* HiFeng' Blog: https://www.hicairo.com/post/57.html  
* wiw' Blog: https://wolan.me/

## 免责声明:
* 本程序仅供学习了解, 非盈利目的，请于下载后 24 小时内删除, 不得用作任何商业用途, 文字、数据及图片均有所属版权, 如转载须注明来源。
* 使用本程序必循遵守部署免责声明。使用本程序必循遵守部署服务器所在地、所在国家和用户所在国家的法律法规, 程序作者不对使用者任何不当行为负责。
