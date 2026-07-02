# 电影天堂去广告 Loon 插件

移除 `api.xhsdns.cn /api/app/init` 下发的开屏广告、首页横幅、播放页广告、分类/我的页横幅，以及底部“游戏”页外部广告大厅入口。

## 安装

在 Loon 中添加插件：

```text
https://raw.githubusercontent.com/sdualasijia/dianyingtiantang_remove_ads/main/remove_xhsdns_ads.plugin
```

启用插件后，确认 MitM 已开启并信任证书，然后杀掉 App 重新打开。

## 处理的配置

- `advlist`
- `advconf.topicIndexList.banner_adv1`
- `advconf.topicIndexList.banner_adv2`
- `advconf.vodDetails.*_adv`
- `advconf.classlist.banner_adv*`
- `advconf.userinfo.banner_adv*`
- `advconf.game_lobby`

