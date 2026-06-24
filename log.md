# 开发日志

## 2026-06-24: 适配 GTNH 2.9.0-beta-1

### 已完成
- 将构建目标升级到 GTNH `2.9.0-beta-1` 相关依赖版本。
- 升级 `gtnhsettingsconvention` 到 `2.0.20`，Gradle wrapper 目标改为 `9.2.1`。
- 将 `NotEnoughItems`、`waila`、`GT5-Unofficial`、`ForgeMultipart` 更新到 2.9 清单版本。
- 增加开发运行时 `org.openjdk.nashorn:nashorn-core:15.4` 依赖，降低 Java 11+ 环境下 JS 引擎缺失风险。
- 关闭旧 Blowdryer Spotless 检查，绕过其在 Gradle 9 下的 `Blowdryer` 属性兼容问题。
- 使用 Java 25 和本地 Gradle 9.2.1 执行 `compileJava` 与 `build`，均已通过。

### 遇到的问题
- **Wrapper 下载超时**：`services.gradle.org` 连接超时，改用本地已缓存 Gradle 9.2.1 运行构建。
- **manifest helper 不可用**：当前项目模板未暴露 `elytraModpackVersion`，改用 2.9 清单中的精确依赖版本。
- **Spotless 脚本不兼容**：旧 Blowdryer Spotless 脚本在 Gradle 9 下失败，已通过 `disableSpotless = true` 规避。

### 决策
- 保留原项目结构，避免大范围迁移到全新的 GTNH 模板。
- 以编译和打包通过为本次升级边界，Waila/GT 具体显示内容仍需要客户端运行验证。
