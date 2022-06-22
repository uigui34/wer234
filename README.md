@azaslaq  搞了个caddy v2ray tor ，默认用vless: https://github.com/mixool/v2ray

[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://dashboard.heroku.com/new?template=https://github.com/uigui34/wer234)  
  
> 提醒： 滥用可能导致账户就被BAN！！！  

TIPS:
* Heroku部署v2ray,添加了caddy和tor的支持，部署后点击View，成功应显示caddy欢迎页面 

* 客户端使用vless websockets tls方式链接服务端  
   

  默认UUID: `3dcda15b-755a-48fe-b012-a4cac2aa9197`  websocket默认路径: `/`  
  
* 可在部署时修改变量UUID和WSPATH，服务端和客户端需相同  
  
* 可以搭配clouflare cdn使用，[参考IBMYes项目的这里](https://github.com/CCChieh/IBMYes#cloudflare-%E9%AB%98%E9%80%9F%E8%8A%82%E7%82%B9%E4%B8%AD%E8%BD%AC)，修改`url.hostname`为**app**分配到的`xxxxxxxxx.herokuapp.com`  
  
* 部署到kintohub: https://github.com/mixool/v2ray/tree/master/kinto
部署到kintohub时，v2ray可以从网络地址读取文件配置，使用自定义的CONFIG更加灵活，支持tor网络，去掉了caddy

部署时需要填写subfolderPath选项为kinto, port: 3001, Deploy Timeout建议设置为五分钟

默认配置是https://github.com/mixool/v2ray/raw/master/kinto/config.json，建议自行复制修改内容后放到GIST，然后设置CONFIG变量为GIST的RAW地址

部署后直接访问External Access返回Bad Request即表示部署成功
