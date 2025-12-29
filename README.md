# 网页工坊 — 说明

- 当前状态：`index.html` 已被替换为**精简版**，移除了大型内联生产包以通过静态校验并方便调试。
- 备份：原始文件已保存为 `index.html.bak`（包含原始内联 bundle），可随时恢复。

## 快速命令
- 静态校验（htmlhint）：
```bash
npx htmlhint index.html
```

- 无头浏览器捕获（将输出写入 `./logs/console.log`）：
```bash
node scripts/capture_console.js
```

- 恢复原始页面（谨慎，可能再次触发 lint 报错）：
```bash
mv index.html.bak index.html
```

## 文件说明
- `index.html` — 当前简化版入口页（用于通过 htmlhint 与运行诊断）。
- `index.html.bak` — 原始备份（包含内联生产 bundle）。
- `scripts/capture_console.js` — 无头捕获脚本（已存在于仓库，用于生成 `./logs/console.log`）。
- `logs/console.log` — 最近一次运行捕获的输出日志。

## 建议
- 若要恢复完整应用并同时通过静态校验，建议将大型内联 bundle 拆出为独立的 `.js`/`.css` 文件并以 `<script src="...">` / `<link>` 引入，或将特殊字符进行合适转义后再校验。

---
如需我把 README 提交（git commit）或把原始 bundle 拆分为独立文件，我可以继续实现。
