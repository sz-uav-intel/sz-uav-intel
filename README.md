# Site — Shenzhen UAV & Low-Altitude Intelligence Briefing

GitHub Pages 静态站骨架（英文，全球可访问）。无构建步骤，纯 HTML/CSS。

## 目录

```
site/
├── index.html                       # 首页：定位、四支柱、往期、订阅、定制服务
├── privacy.html                     # 隐私声明（GDPR 必备）
├── css/style.css                    # 全站样式
└── briefings/
    └── 2026-11-02-issue-001.html    # 第 1 期样例（内容基于已核实的公开信息）
```

## 发布步骤（GitHub Pages）

1. 在 GitHub 建一个**公开仓库**（如 `sz-uav-intel`，或用户名.github.io 仓库则去掉 site 这层目录直接放根）；
2. 把 `site/` 内的全部内容推到仓库根目录：
   ```bash
   cd /mnt/e/Agent-Reach/site
   git init && git add . && git commit -m "site skeleton"
   git remote add origin https://github.com/aaminute-hash/sz-uav-intel.git
   git push -u origin main
   ```
3. 仓库 **Settings → Pages → Branch 选 `main` / `/ (root)` → Save**；
4. 约 1 分钟后访问 `https://aaminute-hash.github.io/sz-uav-intel/`；
5. （可选）绑定自有域名：仓库根加 `CNAME` 文件（内容为域名），域名 DNS 加 CNAME 记录指向 `aaminute-hash.github.io`。

## 上线前必须替换的占位符

- `index.html` / `privacy.html`：`{{your-email@example.com}}`（联系邮箱）、`{{Shenzhen UAV Intelligence}}`（版权主体名）；
- `index.html` 订阅表单 `action="#"`：换成邮件列表服务商端点（Buttondown / Mailchimp / 自托管 Listmonk 均可）；
- 若用个人 GitHub 账号发布，注意 `aaminute-hash` 为账号名，仓库名可自定。

## 每周更新流程

1. 复制 `briefings/2026-11-02-issue-001.html` 为新一期文件（日期命名）；
2. 替换四支柱内容与"一句话综述"（数据底稿来自 `collect-policy.py` / `collect-generic.py` 产出）；
3. 在 `index.html` 的 `<ul class="issues">` 顶部加一行新条目；
4. git push 即自动重新发布。

## 合规提醒（勿删改）

- 全站内容仅基于公开信息，每条关键数据保留 `class="src"` 来源标注；
- 订阅表单的 GDPR 同意 checkbox 与 `privacy.html` 不可移除；
- 站点定位表述保持 "Independent industry intelligence"（中立，不做立场化声明）。
