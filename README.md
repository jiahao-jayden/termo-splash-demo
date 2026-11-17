# Termo splash demo

Termo（象舍）桌面端启动动画演示。像素象来自仓库里的空状态 mascot（`apps/desktop/src/components/sessions/elephant.tsx`），配色与路径保持一致。

在线演示：https://jiahao-jayden.github.io/termo-splash-demo/

打开 `index.html` 即可本地预览（无外部依赖）。按钮 **Replay** 重播，**1× / 0.5×** 切换速度。也可用空格重播、按 `T` 切换速度。若系统开启“减少动态效果”，会直接显示完成后的空状态界面。

## 时序（1×，约 1.2 秒）

1. **0.00–0.70s** 像素方块从四周飞入，按到中心的距离错开，拼成像素象
2. **0.50–0.80s** 大象眨眼、甩一下鼻子，并弹出少量纸屑像素
3. **0.62–0.86s** 终端光标在下方打出 `termo`
4. **0.90–1.20s** 弹簧展开侧栏与终端纸面，进入空状态壳

接入 Tauri 时，可在主窗口 webview 先挂上这一层 splash，等 sidecar / 前端 `ready` 后再卸掉（不要硬等动画播完）。
