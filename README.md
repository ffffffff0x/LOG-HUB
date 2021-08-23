# LOG-HUB

日志分析库,nuclei 的另一种用法

> 密级 : 团队内部项目

---

## 用法

快速打包日志
```bash
find / -name "access.*"

cd /var/log/nginx/
ls -l
# 看下日志大小

# 日志打包拖回本地
tar -zcvf /tmp/target_log.tar.gz /var/log/nginx/
```

调用本地 POC 进行反识别
```bash
mkdir -p /tmp/target_log
tar -zxvf target_log.tar.gz -C /tmp/target_log

nuclei -t /main -target /tmp/target_log -no-interactsh -no-update-templates -nc
```

---

> create by ffffffff0x
