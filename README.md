# AI 运营助手 · Demo

一个纯前端的交互演示，展示"企业消息识别 → AI生成话术建议 → 保存跟进记录"的完整流程。

**这是脱敏后的作品集展示版本**，不是内部工具本体：
- 平台名称、企业名称、政策细节均为虚构
- 不调用任何真实 AI 接口，话术为预设脚本（根据关键词匹配 + AI思考动画模拟真实体验）
- 单个 HTML 文件，无依赖、无后端，手机浏览器直接打开即可用

真实版本是本地部署的 Web 服务（Python + SQLite + DeepSeek API），用于实际运营工作中的企业对接辅助，因涉及内部业务信息不对外公开代码。

## 本地预览

直接双击 `index.html` 用浏览器打开即可，或者：

```bash
python -m http.server 5500
# 浏览器访问 http://localhost:5500
```

## 部署到 GitHub Pages（免费，手机可直接访问）

1. 在 GitHub 上新建一个仓库，比如 `ops-agent-demo`（设为 Public）
2. 把这个文件夹的内容推上去：
   ```bash
   cd ops-agent-demo
   git init
   git add index.html README.md
   git commit -m "AI运营助手 demo"
   git branch -M main
   git remote add origin https://github.com/<你的用户名>/ops-agent-demo.git
   git push -u origin main
   ```
3. 进入仓库 → Settings → Pages → Source 选择 `main` 分支 / `/ (root)` 目录 → Save
4. 等 1-2 分钟，访问 `https://<你的用户名>.github.io/ops-agent-demo/` 即可，手机浏览器直接打开这个链接就能演示

## 项目亮点（面试可讲的点）

- **上下文注入而非对话记忆**：每次"AI分析"都基于企业档案数据动态生成上下文，而不依赖多轮对话记忆——对应真实版本里"避免长对话 prompt 约束力衰减"的架构设计
- **交互设计还原真实工作流**：搜索企业 → 加载历史档案 → 粘贴消息 → 识别类型+生成话术 → 保存更新台账，完整对应实际运营的工作步骤
- **零成本可复现**：demo 本身不依赖任何后端/API/数据库，任何人打开链接都能立刻体验，不用配置环境
