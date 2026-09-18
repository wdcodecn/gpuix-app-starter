# gpuix-app-starter

[English](README.md)

这是由 [`gpuix-android`](https://github.com/wdcodecn/gpuix-android) 生成的可运行示例，
并使用 [`gpuix-base-ui`](https://github.com/wdcodecn/gpuix-base-ui) 组件。React 负责描述 UI，GPUIX/wgpu 负责原生绘制，
JavaScript 运行在独立 Hermes 中，不包含 WebView 或 React Native View 系统。

## 开发

```sh
gh repo create my-app --public \
  --template wdcodecn/gpuix-app-starter \
  --clone
cd my-app
bun install
bun run typecheck
bun run dev
```

## Android

```sh
bun run gpuix:doctor
bun run gpuix:build
bun run gpuix:run -- <ADB_SERIAL>
```

发布构建：

```sh
gpuix build --release       # 本地 release APK
gpuix build --aab           # Google Play App Bundle
```

`gpuix.android.json` 是 Android 交付配置。`versionCode` 每次发布必须递增；当前
starter 的 release 构建使用 debug keystore 仅用于本地验收，商店发布前要配置正式签名。

框架修复应提交到 `gpuix-android`，可复用组件应提交到 `gpuix-base-ui`；本仓库只维护
小型示例应用和项目级配置。
