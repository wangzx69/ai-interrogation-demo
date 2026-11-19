# 雾港疑案 · AI 审讯室（v4）

一个用「自由提问 + 出示证据 + 语气选择」推进的 AI 推理游戏 Demo。

- **3 个案件**：雾港疑案 / 雨夜民宿 / 远洋货轮
- **每局随机案件 + 随机凶手**：3 案件 × 3 凶手 = 9 种组合
- **9 种「角色 × 凶手」专属内容**：每个凶手有自己的独白、关键证据反应、结局；每个无辜者有不同的证词
- 3 名嫌疑人，各怀秘密、各说各话
- 10 次提问、3 处现场、1 次指认（凶手 + 2 条证据）
- 三种语气：共情（+信任）/ 施压（+压力）/ 套话（中性）
- 压力 >70 角色会说漏嘴；信任 >70 会主动给信息
- 单文件 HTML，离线可玩；填入 OpenAI 兼容接口即可让 AI 实时扮演角色
- 一局 10–15 分钟

## 玩法

1. 读案卷，了解死者与三名嫌疑人
2. 选择嫌疑人，自由输入问题
3. 搜查现场（各消耗 1 次提问）获得线索
4. 用线索逼问，观察谁改口
5. 指认凶手；只指认对但没拿关键证据，也算失败

## 本地运行

直接用浏览器打开 `index.html` 即可（推荐 Chrome / Edge）。

## 部署到 GitHub Pages

1. 新建仓库，例如 `ai-interrogation-demo`
2. 把 `index.html` 上传到仓库根目录
3. Settings → Pages → Build and deployment → Deploy from a branch
4. Branch 选 `main`，目录选 `/ (root)`，保存
5. 一分钟后访问 `https://<你的用户名>.github.io/ai-interrogation-demo/`

## 接入 AI（可选）

打开页面右上角「AI 设置」，填入：

- 接口地址：任意 OpenAI 兼容的 Chat Completions 地址
  - DeepSeek：`https://api.deepseek.com/v1/chat/completions`
  - OpenAI：`https://api.openai.com/v1/chat/completions`
- API Key
- 模型：如 `deepseek-chat`、`gpt-4o-mini`

Key 只保存在当前页面的 `sessionStorage`，关闭页面即清除。

> 浏览器直连大模型可能遇到 CORS。若接口不支持浏览器跨域，请用本地代理或服务端转发；离线模式不受影响。

## 文件

- `index.html`：游戏本体（数据、Prompt、逻辑、样式都在里面）
- `雾港疑案-AI审讯室-产品说明.pdf`：产品设计说明（玩法判断、AI 设计、指标、迭代）

## 设计说明

产品说明覆盖：

- 为什么做「审讯 + AI」
- 核心循环、乐趣来源、不爽点与对策
- 角色秘密/谎言/被证据逼问后的反应
- Prompt 结构、一致性、防出戏、成本
- 验证指标（完成率、破案率、平均提问数、角色可信度、重玩意愿）

## 作者

王紫萱 · 中山大学 数学与应用数学 · 2026 届
