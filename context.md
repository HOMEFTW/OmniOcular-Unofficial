# 项目上下文

## 基本信息
- Mod 名称：Omni Ocular Unofficial
- Mod ID：`OmniOcularUnofficial`
- 包名：`me.exz.omniocular`
- 目标环境：Minecraft `1.7.10` + Forge `10.13.4.1614` + GTNH `2.9.0-beta-1`

## 已实现内容

### 功能概览
- 作为 Waila 插件读取 TileEntity、Entity、FMP part 和 Tooltip 的 NBT。
- 通过 XML 配置和 Nashorn JavaScript 生成 Waila 显示行。
- 支持服务端同步 XML 配置到客户端。

### Mixins
- `me.exz.omniocular.mixins.MixinHUDHandlerFMP`：注入 `mcp.mobius.waila.handlers.HUDHandlerFMP#getWailaBody`，让 FMP part 也走 OmniOcular 的 XML/脚本显示逻辑。

### 主要依赖
- `NotEnoughItems:2.8.101-GTNH:dev`
- `waila:1.19.30:dev`
- `GT5-Unofficial:5.09.52.594:dev`，开发运行时
- `ForgeMultipart:1.7.7:dev`，开发运行时
- `org.openjdk.nashorn:nashorn-core:15.4`，开发运行时

## 构建说明
- `gtnhsettingsconvention`：`2.0.20`
- Gradle wrapper 目标：`9.2.1`
- Java：已用 `C:\Program Files\Zulu\zulu-25` 验证。
- 当前旧 Blowdryer Spotless 脚本在 Gradle 9 下不兼容，项目设置 `disableSpotless = true`。

## 验证状态
- `compileJava`：通过。
- `build`：通过。
- 客户端运行验证：未完成。
