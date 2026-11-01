# Japan Travel Guide · 日本自由行规划

网站：https://d68391156-web.github.io/

本次源码版本：7a4f819（本地提交），已移除ISIC办卡与回本计算。

- 2027年1月25日至2月7日，14天13晚；东京5晚、京都3晚、大阪5晚。
- 保留11天历史方案、地图、汇率、机票与住宿手动报价和预算。
- 新增交通比较、夜巴情景、实际支出账本与JSON备份、2026年11月退税规则及计算器。
- 74个地点，未核实票价和营业日历明确标注；新增图片标为城市示意。
- TypeScript、生产构建和50项回归测试通过。

## 源码与部署

可维护的Next.js + TypeScript工程保存在 `japan-travel-source.zip`，包含package.json、锁文件、组件、数据、测试、public资源和文档。解压后运行 `pnpm install --frozen-lockfile`、`pnpm test`、`pnpm typecheck`、`pnpm build`。源码并非从编译JavaScript完整反编译取得，恢复经过见压缩包内docs/RECOVERY.md。

此次网页上传沿用仓库既有GitHub Actions部署：先解压原始静态包，再解码并覆盖 `currency-update.b64`。虽然沿用旧文件名，更新包现包含完整的最新静态导出，不仅是汇率功能。main分支提交后由现有Actions发布；部署成功与否请查看Actions。

解压源码后的 `启动日本旅行规划.command` 可运行本地成品（须先生成out）。新浏览器默认核心方案，已有行程缓存不自动覆盖，可在「我的行程」载入14天核心方案。
