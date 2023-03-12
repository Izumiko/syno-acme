# syno-acme
通过acme协议更新群晖HTTPS泛域名证书的自动脚本

使用方法参见: [http://www.up4dev.com/2018/05/29/synology-ssl-wildcard-cert-update/](http://www.up4dev.com/2018/05/29/synology-ssl-wildcard-cert-update/)

## 简要说明

1. 把本项目上传到群晖
2. 编辑config配置文件（DOMAIN，DNS，SERVER，代理等）
3. 找到cert-up.sh的绝对路径（记为/cert_path/cert_up.sh方便叙述）
4. 创建定时任务，以root用户运行，时间设为每周一即可。命令内容为
   > `/cert_path/cert_up.sh generate >> /cert_path/update.log 2>&1`
5. 创建成功后，右键手动运行一次该任务，然后确认证书成功申请并更新后，把上述命令修改为如下内容：
   > `/cert_path/cert_up.sh cron >> /cert_path/update.log 2>&1`
