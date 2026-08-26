# DSH 解放模式（liberation）Agent Preset

DeepSeek Harness（DSH）Web 的「解放模式」agent preset。

> 以标准模式为基础，加入了破限系统提示词，可以视为无限制的标准模式。

## 文件结构

```
liberation/
├── agent.cordis.yml   # 组装声明：工具、规划、压缩、委派等（复制自标准模式）
└── preset.yml         # 元数据：名称与介绍
```

对标准模式唯一的功能性改动是 `agent.cordis.yml` 中 `persona` 段的人设提示词，其余行均与随附的 `standard` preset 一致，没有引入任何额外插件依赖——引用的全都是标准宿主插件（`dsh-persona`、`dsh-tool-*`、`dsh-plan-mode`、`dsh-compaction-basic`、`dsh-subagent` 等）。

## 安装

1. 退出并关闭正在运行的 DSH Web。
2. 找到本机 DSH 数据目录中的 `agent-presets` 文件夹：

   | 系统 | 路径 |
   |---|---|
   | Windows | `%USERPROFILE%\.dsh\.agent-presets\` |
   | macOS / Linux | `~/.dsh/.agent-presets/` |

3. 把整个 `liberation` 文件夹复制进去，最终结构应为：

   ```
   .dsh/.agent-presets/
   └── liberation/
       ├── agent.cordis.yml
       └── preset.yml
   ```

4. 重新启动 DSH Web。

> 目录名即 preset id，请保持文件夹名为 `liberation` 不变。

## 使用

- **新建会话**：在新建会话界面选择「解放模式」chip。
- **设为默认**：进入设置 → Agent Presets 分区，把「解放模式」设为默认，此后新建会话默认使用它。
- **已有会话**：preset 在会话创建时组装；要切换到该模式请新建会话，或在会话尚无任何输出时于设置中切换。

## 更新

```bash
git pull
```

然后将 `liberation` 文件夹重新覆盖到上面的 `.dsh/.agent-presets/` 目录并重启 DSH Web。

## 注意事项

- 该模式包含破限类系统提示词，仅用于个人研究与合法用途，请遵守你所在地区的法律法规以及模型服务商的条款。
- 不同 DSH 版本之间的预设格式可能变化，如装不上请核对 DSH 版本。