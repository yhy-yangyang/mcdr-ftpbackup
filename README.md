# MCDR-FTPBackup

一个为 Minecraft 服务器提供备份与 FTP 远程同步功能的 MCDReforged 插件。

---

## 功能特性
- **一键备份**：自动压缩服务器文件并支持断连保护
- **远程同步**：将备份文件上传至远程 FTP 服务器
- **匹配编码**：自动匹配FTP服务器的编码
- **智能清理**：保留指定数量的本地备份文件
- **安全模式**：关闭服务器后再执行备份
- **权限管理**：可配置不同命令的权限等级

---

## 安装指南
1. 将插件文件放置于 MCDR 的 `plugins` 目录
2. 首次运行会自动生成配置文件 `config/config.json`
3. 根据服务器环境修改配置文件（配置说明见下文）

---

## 配置说明
```json
{
  "host": "ftp.example.com",       // FTP 服务器地址
  "port": 21,                      // FTP 端口
  "username": "anonymous",         // 登录用户名
  "password": "",                  // 登录密码
  "prefix": "!!fb",                // 命令前缀
  "server_dir": "./server",        // 服务器目录
  "keep_local_backups": 3,         // 本地保留备份数量
  "required_permission": 3,        // 操作所需权限等级
  "exclude_patterns": [            // 需要排除的文件
    "logs",
    "*.tmp",
    "*.lock"
  ]
}
```

---

## 命令列表
<font size="3">注意:本文档假定你使用`!!fb`作为 MCDR 命令的前缀</font>

- `!!fb help` - 显示帮助信息
- `!!fb test` - 测试与FTP服务器的连接
- `!!fb make` - 创建一个备份并上传到FTP服务器
---

## 注意事项
1. 在插件加载时会测试与FTP服务器的连接
2. 首次使用前需要在`config.json`文件中修改FTP服务器有关设置
3. 备份完毕后会在`backups`文件夹内保留备份，保留数量可在配置文件内修改
4. 排除的文件以unix shell风格匹配

---

## 许可证
本项目基于 Apache License 2.0 发布

---

## 贡献
欢迎提交 Issue 和 Pull Request！
