# obsidian-message-journal

`obsidian-message-journal` 是一个 Obsidian 插件，用于自动解析 QQ 和微信消息，筛选重点联系人或关键词的消息，利用大语言模型自动生成每日总结，生成符合个人风格的日记内容。

# 项目进展
- **2014-11-1**：创建基本obsidian库，完成相关知识构建


# 项目预期
## 功能概述

- **消息解析**：自动从 QQ 和微信的消息数据库中提取最新消息。
- **增量更新**：只处理前一天的新消息，避免重复解析。
- **重点筛选**：按照预先配置的联系人或关键词筛选重要消息。
- **内容归纳**：调用 OLLAMA 大语言模型对重要消息进行自动归纳。
- **每日个人日记**：基于重要消息生成每日总结和个人日记内容。
- **数据存储**：将日记和消息摘要存储为每日的 DB 数据库文件，方便查询和分析。

## 安装

### 1. 手动安装

1. 克隆本仓库到本地插件目录：

   ```bash
   git clone https://github.com/yourusername/obsidian-message-journal.git
   ```

2. 将该文件夹移动到 Obsidian 插件目录下的 `.obsidian/plugins` 文件夹。
3. 在 Obsidian 中，前往 `Settings -> Community plugins` 并启用 `obsidian-message-journal` 插件。

### 2. 从 Obsidian 插件市场安装

如果此插件已发布到 Obsidian 社区插件市场，您可以直接从 Obsidian 中的插件市场进行安装。

## 配置

1. 在 Obsidian 中打开 `Settings -> Plugin Options`，找到 `obsidian-message-journal` 配置界面。
2. 设置 QQ 和微信消息的存放目录。
3. 输入重点关注的联系人名称或关键词，系统将自动筛选包含这些关键词或联系人的消息。
4. 配置 OLLAMA 大语言模型的 API Key 或相关访问信息（若需要）。

## 使用说明

### 消息解析与日记生成

- 安装并配置插件后，插件将自动在每日凌晨执行以下操作：
  - 解析 QQ 和微信消息库，提取前一天的消息。
  - 根据重点关注的联系人或关键词筛选出相关消息。
  - 调用 OLLAMA 大语言模型对筛选后的消息进行归纳总结，生成简洁的每日重要消息摘要。
  - 生成符合个人风格的日记内容，并存储为当天的 DB 数据库文件。
  
### 查看日记

- 您可以在 Obsidian 中通过每日的特定笔记（如“每日记录”）查看生成的日记内容。
- 数据也存储在 DB 数据库文件中，便于后续查询和分析。

## 示例

生成的日记示例如下：

```
## 2024-01-01 日记

### 重点消息摘要
- 与 [好友1] 的交流：关于项目的最新进展和合作机会
- [家人] 的消息：提醒注意健康和休息
- 其他重要提醒：天气预报提示

### 今日总结
今天的交流让我意识到新的工作机会以及家人对我的关心。整体感觉很充实。
```

## 常见问题

### 1. 插件无法解析消息文件？
确保您已经正确配置了 QQ 和微信的消息存放目录，并确保 Obsidian 对该目录有读取权限。

### 2. 日记内容未生成？
请检查您的 OLLAMA 大语言模型 API Key 是否正确配置，或查看错误日志以获取更多信息。

## 开发

### 构建插件

如果您希望对插件进行开发或修改：

1. 克隆此仓库：
   ```bash
   git clone https://github.com/gjhhust/obsidian-message-journal.git
   ```
2. 安装依赖：
   ```bash
   npm install
   ```
3. 构建项目：
   ```bash
   npm run build
   ```

## 贡献

欢迎提出 Issue 或 Pull Request！您的反馈将帮助我们不断改进这个插件。

## 致谢
本项目的知识基于一下项目获取，非常感谢:
- QQ与微信消息解密与解析：
   - [windows取证之导出微信&QQ聊天记录](https://saucer-man.com/information_security/1038.html)
   - [解密qq数据库](https://github.com/saucer-man/qq_msg_decode?tab=readme-ov-file)
- 接入ollama: 

## 许可证

本项目禁止商用 [MIT 许可证](LICENSE)。