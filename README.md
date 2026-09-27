# zshtech.com

中晟鑫财科技（北京）有限公司官网。纯静态页面，无构建步骤，托管在 Cloudflare Pages。

用途：D-U-N-S 申请，以及 Google Play / App Store 组织账号申请时的企业官网核验。

## 目录结构

```
index.html        首页（What we do / Company / Contact）
privacy.html      隐私政策，线上路径 /privacy
terms.html        服务条款，线上路径 /terms
404.html          Cloudflare Pages 自动用作 404 页
assets/styles.css 全站样式
favicon.svg       文字标识（无 Logo，用 ZS 字母块）
robots.txt        允许收录，指向 sitemap
sitemap.xml       三个页面
_headers          Cloudflare Pages 响应头
```

## 部署

Cloudflare Pages 连接本仓库后，用以下设置：

| 配置项 | 值 |
| --- | --- |
| Framework preset | None |
| Build command | 留空 |
| Build output directory | `/` |
| Production branch | `main` |

推送到 `main` 即自动发布。自定义域名在 Pages 项目的 Custom domains 里绑定 `zshtech.com`（建议同时绑定 `www.zshtech.com` 并重定向到主域名）。

`privacy.html` 与 `terms.html` 在 Pages 上通过 `/privacy`、`/terms` 访问，站内链接和 sitemap 都用这两个无后缀路径。

## 本地预览

```bash
npx serve .
```

直接双击 `index.html` 也能看，但 `/privacy`、`/terms` 这类无后缀链接只有起了服务才正确。

## 页面上的事实来源

以下内容与工商登记、申请材料必须保持一致，改动前先核对营业执照：

| 项目 | 当前值 |
| --- | --- |
| 中文法定名称 | 中晟鑫财科技（北京）有限公司（全角括号） |
| 英文名称 | Zhongsheng Xincai Technology (Beijing) Co., Ltd.（音译，执照无英文名） |
| 统一社会信用代码 | 91110117MACQA3W17C |
| 成立日期 | 2023-07-11 |
| 登记机关 | 北京市平谷区市场监督管理局 |
| 办公地址 | 北京市平谷区金海湖镇韩庄南大街111号-233921 |
| 英文地址 | No. 111-233921, Hanzhuang South Street, Jinhaihu Town, Pinggu District, Beijing 101201, China |
| 电话 | +86 132 4172 0368 |
| 邮箱 | admin@zshtech.com |

英文名称在网站、邓白氏档案、Apple 与 Google 申请表里必须写成同一种形式。

页面上不出现：股东与监事姓名、年报中 133 开头的财务会计电话、「集群注册」字样、douyincrm.com / douyincrm.cn、京ICP备2023020005号。

## 提交申请前需要完成

- 开通 admin@zshtech.com（计划用 Google Workspace），审核邮件会发到这个地址。
- 确认 +86 132 4172 0368 能接听邓白氏核验来电。
- 站点绑定 zshtech.com 并可通过 HTTPS 公开访问。

## 后续需要改页面的情况

- 游戏上架后：在首页 What we do 里补上应用名称与商店链接。
- 接入广告 SDK 或内购：`privacy.html` 与 `terms.html` 需要另写一版，说明收集的数据、支付与退款规则，并更新生效日期。
- 若为 zshtech.com 办理 ICP 备案：在页脚加备案号并链接到 https://beian.miit.gov.cn。
