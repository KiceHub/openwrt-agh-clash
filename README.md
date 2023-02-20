# openwrt-agh-clash
AdGuardHome and Clash for openwrt.
- AGH: 接管DNS、分流判断
- Clash: 全局模式 or MATCH,代理
- 支持IPv4/IPv6
- 使用TPROXY，可能与安装docker的固件冲突（可解决）
- 使用AGH的ipset设置，细化分流
- 默认x86，其他CPU需替换对应的clash AdGuardHome

## 分流规则
- cn and no gfw ip -- DIRECT
- gfw ip -- Clash

## 使用说明
- 授予0755权限
> /opt/AdGuardHome/AdGuardHome
> /opt/Clash/clash-linux-amd64
> /opt/Clash/rules/clash.include
- 创建软链接（或更改init.d内的可执行文件路径）
> /opt/AdGuardHome/AdGuardHome --> /usr/bin/AdGuardHome
> /opt/Clash/clash-linux-amd64 --> /usr/bin/Clash
- 添加到\etc\config\firewall，而不是替换
- （可选）拦截53请求


