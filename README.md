## 中文搜索结果黑名单

垃圾站点出现在 Google、百度的中文搜索结果中，实在是恶心—— 于是这个黑名单就这么出来了。

原项目：https://github.com/cobaltdisco/Google-Chinese-Results-Blocklist

由于原项目不支持 [翻译垃圾再利用](https://greasyfork.org/zh-CN/scripts/389270) 脚本，于是做了一个修改版

## 如何使用

安装以下插件导入黑名单，插件选其中之一即可。

强烈建议使用 **uBlacklist**，因为该插件可以对搜索结果标题进行匹配 (即下方提到的“模糊匹配”)。例如，Google 搜索结果中可能有成百上千的“小 X 百科网”、“小 X 知识网”，以域名匹配的方式几乎是不可能的 (即下方提到的“精确匹配”)。这时用正则模糊匹配结果标题，将会非常简单。

同理，由于 **Google Hit Hider by Domain** 和 **AC-baidu** 没有匹配标题的功能，屏蔽效果会比 **uBlacklist** 差。

### 屏蔽 Google 中文搜索结果

**1. uBlacklist** 

[Chrome Web Store](https://chrome.google.com/webstore/detail/ublacklist/pncfbmialoiaghdehhbnbhkkgmjanfhe)

[Firefox Add-ons](https://addons.mozilla.org/en-US/firefox/addon/ublacklist/)

[Mac App Store](https://apps.apple.com/app/ublacklist-for-safari/id1547912640))

- 将以下 2 个链接，通过点击 Add a subscription 添加到 Subscription 分类下。


  - `https://ghproxy.com/https://raw.githubusercontent.com/thomaswcy/Google-Block-List/master/uBlacklist_subscription.txt`：该匹配方式主要是通过 `*://*.xxxx.com/*` 的方式来匹配搜索结果，进行过滤。基本不会有误杀。

  - `https://ghproxy.com/https://raw.githubusercontent.com/thomaswcy/Google-Block-List/master/uBlacklist_match_patterns.txt`：该匹配方式主要是通过如 `*://*/list.php?s=*`、`title/小.(百科|知识)网/` 的方式来匹配搜索结果，进行过滤。存在小范围的误杀。

    - 请仔细查看当前模糊匹配列表 (下方列表为最新规则)，若会击中自己经常使用的网站，请自行修改规则配置到插件中，防止被误杀。

```
        *://*/so.php
        *://*/so.php?s=*
        *://*/cha.php?s=*
        *://*/list.php?s=*
        *://*/?s=*
        *://*/so/*
        title/^小.(百科|知识)网$/
        title/^.*[ ]-[ ]小.(百科|知识)网$/
        title/.*点击一次就可以出国/
        title/.*一键访问国外网站/
```

### 屏蔽百度中文搜索结果

**1. Google Hit Hider by Domain** (下载地址：[GreasyFork](https://greasyfork.org/zh-CN/scripts/1682-google-hit-hider-by-domain-search-filter-block-sites))

- 同 Google 方案操作。

**2. AC-baidu** (下载地址：[GreasyFork](https://greasyfork.org/zh-CN/scripts/14178-ac-baidu-%E9%87%8D%E5%AE%9A%E5%90%91%E4%BC%98%E5%8C%96%E7%99%BE%E5%BA%A6%E6%90%9C%E7%8B%97%E8%B0%B7%E6%AD%8C%E5%BF%85%E5%BA%94%E6%90%9C%E7%B4%A2-favicon-%E5%8F%8C%E5%88%97))

- 开启“附加2-自主拦截域名”，点击 DIY，将[该列表](https://ghproxy.com/https://raw.githubusercontent.com/thomaswcy/Google-Block-List/master/GHHbD_perma_ban_list.txt)中的网址导入。
> 注：这个脚本也会同时对搜狗、谷歌、必应搜索结果同时产生影响。

## 反馈

在 [Issues](https://github.com/thomaswcy/Google-Block-List/issues) 留言
