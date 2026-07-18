# 工作集与抖动：从 Denning 1968 到 LLM KV Cache

两个交互式教学页面，纯静态单文件（无外部依赖，支持深色模式），部署在 GitHub Pages：

- **`index.html` — 工作集与抖动：看懂 Denning 的 1968**
  页面引用串 + 滑动窗口的工作集演示、s(τ) 膝点曲线、缺页代价与生存期曲线、
  抖动模拟器（U(N) = 1 − bᴺ，可开启工作集准入控制对照）。
- **`kvcache.html` — KV Cache 的工作集与雪崩（续篇）**
  围绕四个关键点：① 一个 session 的需求 = 全部前缀（一轮一行的 prefill 账单图，
  部分尾部逐出）；② miss 代价 R ≈ context/轮长 ⇒ 99% 命中率只值 50% 效率（e–h 曲线）；
  ③ 超线即雪崩且 GPU 利用率恒 100%（stack distance 柱图：柱高与容量无关，
  M 只是一条可拖的线，高出线的部分 = 重算量；雪崩线 N·c̄ = M 的 goodput 悬崖）；
  ④ 药方 = 准入控制。
  第 2 节账单图与第 4 节柱图共用同一份 5 会话数据（会话 1 是账单主角）。

## 本地查看

直接用浏览器打开对应 HTML 即可。

## 部署

`.github/workflows/pages.yml` 在推送到 `main` 后自动部署；
首次使用需在 Settings → Pages 将 Source 设为 GitHub Actions。
线上地址：https://simpx.github.io/thrashing/
