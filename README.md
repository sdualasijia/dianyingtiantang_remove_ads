# 电影天堂去广告 Loon 插件

移除 `api.xhsdns.cn` / `api.dyapis.cn` 下发的开屏广告、首页横幅、播放页贴片/暂停广告、分类/我的页横幅，以及底部“游戏”页外部广告大厅入口。

新版电影天堂已经切换到 `api.dyapis.cn`，开屏配置也从 `advconf.splash` 移到了 `advconf.launch.splash`；插件同时兼容新旧域名和新旧字段。

## 安装

在 Loon 中添加插件：

```text
https://raw.githubusercontent.com/sdualasijia/dianyingtiantang_remove_ads/main/remove_xhsdns_ads.plugin
```

启用插件后，确认 MitM 已开启并信任证书，然后杀掉 App 重新打开。如果仍然显示缓存的旧开屏，清除一次 App 缓存或重装。

## 处理的配置

- `advlist`
- `advconf.launch.splash`（新版开屏）
- `advconf.launch.popup`
- `advconf.home.banners`
- `advconf.home.banner_adv1/2`
- `advconf.home.online_time_adv`
- `advconf.topicIndexList.banner_adv1/2`
- `advconf.vodDetails.*_adv`
- `vod_play_url[].ad`
- `/api/vod/play` 返回体里的 `ad`
- `advconf.classlist.banner_adv*`
- `advconf.userinfo.banner_adv*`
- `advconf.game_lobby`

## 兼容性

- 旧版接口：`https://api.xhsdns.cn/api/app/init|vod/details|vod/play`
- 新版接口：`https://api.dyapis.cn/api/app/init|vod/details|vod/play`
- 两个域名都加入 MITM；返回体的 `data` 仍按原有 AES-128-CFB 格式解密和回写。

尚未覆盖的新版广告位，请提交 Issue，并附上脱敏后的请求 URL、加密响应结构和应用版本。不要上传 Cookie、Token、账号或设备标识。
