# ExcellentMInecraftscripts

`The Poetry Of Winter` 行为包脚本侧的 TypeScript 源码目录。

本目录主要包含两条玩法线：

- `POM`（主玩法）
- `DEC`（扩展系统与内容）

## 目录结构

- `src/pom`：POM 玩法逻辑（服务端、客户端、实体、任务、UI、遗迹等）
- `src/dec`：DEC 玩法逻辑（服务端、客户端、Boss、任务等）
- `src/modules/exmc`：通用框架（事件系统、服务端/客户端基类、工具）
- `src/modules/interact`：协议与交互桥接
- `src/filepack`：打包后的大体量数据文件（请谨慎修改）
- `src/test`：实验与测试脚本
- `src/pom.ts`：POM 入口
- `src/dec.ts`：DEC 入口

## 构建映射

编译配置由以下文件控制：

- `src/TPOW/WPB/scripts/tsconfig.json`

关键映射关系：

- 输入目录：`ExcellentMInecraftscripts/src`
- 输出目录：`src/TPOW/WPB/scripts/out`
- 输出入口：`out/pom.js`、`out/dec.js`

当前行为包 `manifest.json` 的脚本入口为：

- `scripts/out/pom.js`

## 本地编译（示例）

在 `src/TPOW/WPB/scripts` 目录执行：

```bash
tsc -p tsconfig.json
```

## 维护建议

- 优先修改 `src/pom`、`src/dec`、`src/modules/exmc` 中的业务逻辑代码。
- 非必要不要手动编辑 `src/filepack`，避免破坏打包产物结构。
- 修改事件系统或核心框架时，重点检查：
  - 订阅/反订阅是否成对
  - 异常是否有记录与上报
  - 大循环逻辑是否分帧执行（避免卡顿）
