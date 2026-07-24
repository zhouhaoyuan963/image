# image

截图公网图床 —— 配合 ZCode 的 `screenshot-reader` skill 使用。

## 用途

ZCode 的 `analyze_image` 工具（基于视觉模型）只能读取**公网可访问的图片 URL**。
本仓库作为 public 图床，把本地截图变成可被视觉模型读取的 raw URL。

## 工作流

1. 用户截图（Snipaste 自动存到 `桌面/截图/`）
2. 调用 `screenshot-reader` skill
3. skill 自动：读取截图 → push 到本仓库 → 得到 raw URL → 调 analyze_image 读图
4. 返回对截图的语义理解

## 目录约定

截图按日期归档，避免根目录堆积：

```
/2026-07/              # 年-月
  ├── Snipaste_xxx.png
  └── ...
/2026-08/
```

## 清理

本仓库只作图床，不存代码。读取完毕后，旧的截图可定期清理（raw URL 在 push 期间有效）。
