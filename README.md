# QARPilot 上架用网站（草稿）

生成：2026-10-09 ｜ 负责人：牛牛（行政助理）
目录：`~/.hermes/profiles/niuniu/drafts/web/`

## 文件

| 文件 | 用途 | App Store 需求 |
|---|---|---|
| `index.html` | 落地页（公司介绍 + 产品简介） | 可作「营销网址」，非必填 |
| `privacy.html` | 隐私政策（中英双语） | **必填**：App Store Connect → 隐私政策 URL |
| `support.html` | 技术支持页 | **必填**：App Store Connect → 支持 URL |
| `style.css` | 全站样式（深色，移动端适配） | — |

## 部署（先挂境外免费托管，不被 ICP 备案卡住）

**方案 A｜Vercel（推荐，最快）**
1. 把本目录内容放进一个 GitHub 仓库（或直接用 Vercel CLI：`npx vercel --prod` 在目录内执行）。
2. Vercel → Add New Project → 导入仓库 → Framework 选 `Other` → Deploy。
3. 得到 `https://<project>.vercel.app`，三个页面路径：`/`、`/privacy.html`、`/support.html`。
4. 之后可在 Vercel 绑定自有域名 `mobiusstack.com`（**注意**：绑定国内服务器域名解析前不影响 App Store 使用）。

**方案 B｜GitHub Pages**
1. 新建仓库 → 上传本目录 → Settings → Pages → Source: `main` / root。
2. 访问 `https://<user>.github.io/<repo>/privacy.html`。

> 境外托管无需 ICP 备案；国内官网（`mobiusstack.com`）在备案号下发后另行部署。

## 上线前必须替换的占位符

- `【备案号待下发后填写】`（3 处：index / privacy / support）——**ICP 备案号下发后**填云南省备案号，格式 滇ICP备XXXXXXXX号。
- `【待上线日】`（隐私政策生效日期）。
- 支持页第 5 条「是否收费/内购」——等上架形态（免费无内购 / 订阅）拍板。
- 品牌名与 App 名：当前用 **QARPilot**（与 `mobiusstack.com` 品牌中性化一致；若最终名改 Mobius Pilot / Pilot Loop / FlarePath，需全站替换）。
- 邮箱：当前统一用 `honglin.li@mobiusstack.com`。若后续开通 `support@ / privacy@`，替换对应页面的邮箱。

## 已知待办

- [ ] 用户在手机/电脑上确认文案与配色 → 定稿。
- [ ] 上架形态拍板后更新 support 页第 5 条 + privacy 页第三方服务段。
- [ ] 备案号下发后回填 3 处。
- [ ] 部署后把 `/privacy.html` 与 `/support.html` 填进 App Store Connect。
