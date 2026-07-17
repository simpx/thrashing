# 工作集与抖动 — 可视化解读 Denning (1968)

一个单页交互式可视化，帮助理解 Peter Denning 1968 年两篇经典论文中的核心概念：

- **The Working Set Model for Program Behavior**（CACM, 1968）— 工作集 W(t, τ)、程序局部性、窗口 τ 的选择
- **Thrashing: Its Causes and Prevention**（AFIPS FJCC, 1968）— 抖动的成因（内存过度分配的正反馈崩溃）与工作集准入控制

## 内容

- 可拖动的页面引用串 + 滑动窗口演示，实时显示工作集内容与大小
- 平均工作集大小 s(τ) 曲线（递增凹函数与拐点）
- 抖动模拟器：固定 60 帧内存，拖动进程数观察 CPU 利用率的断崖式崩塌，可开启工作集准入控制对照

页面为纯静态单文件（`index.html`），无外部依赖，支持深色模式。

## 本地查看

直接用浏览器打开 `index.html` 即可。

## 部署到 GitHub Pages

仓库已包含 `.github/workflows/pages.yml`，推送到 `main` 分支后自动部署。
首次使用需在仓库 **Settings → Pages** 中将 **Source** 设为 **GitHub Actions**。
