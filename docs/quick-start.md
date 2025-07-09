# 🚀 PowerAutomation v4.1 快速开始指南

欢迎使用PowerAutomation v4.1！本指南将帮助您在5分钟内开始使用AI自动化的强大功能。

## 📋 准备工作

### 系统要求
- **操作系统**: macOS 10.15+ / Windows 10+ / Ubuntu 20.04+
- **内存**: 最低8GB RAM，推荐16GB
- **存储**: 2GB可用空间
- **网络**: 互联网连接（用于Claude API）

### 获取Claude API密钥
1. 访问 [Anthropic Console](https://console.anthropic.com/)
2. 注册或登录账户
3. 创建新的API密钥
4. 保存密钥备用

## 🍎 macOS安装（推荐）

### 第一步：下载部署包
```bash
# 下载主程序包
curl -L -O https://github.com/alexchuang650730/aicore0707/raw/main/deployment/devices/mac/PowerAutomation_v4.1_ClaudEditor_Mac.tar.gz

# 下载校验和文件
curl -L -O https://github.com/alexchuang650730/aicore0707/raw/main/deployment/devices/mac/PowerAutomation_v4.1_ClaudEditor_Mac.tar.gz.sha256

# 验证文件完整性
shasum -a 256 -c PowerAutomation_v4.1_ClaudEditor_Mac.tar.gz.sha256
```

### 第二步：解压和安装
```bash
# 解压文件
tar -xzf PowerAutomation_v4.1_ClaudEditor_Mac.tar.gz

# 进入项目目录
cd aicore0707

# 运行自动安装程序
./install_mac.sh
```

安装程序将自动：
- ✅ 检查系统要求
- ✅ 安装Python 3.11和Node.js
- ✅ 安装项目依赖
- ✅ 创建桌面快捷方式
- ✅ 配置环境变量

### 第三步：配置Claude API
```bash
# 编辑配置文件
nano config/claudeditor_config.yaml

# 或使用其他编辑器
code config/claudeditor_config.yaml
```

在配置文件中添加您的API密钥：
```yaml
claude:
  api_key: "your-claude-api-key-here"
  model: "claude-3-sonnet-20240229"
  max_tokens: 4000
  temperature: 0.7
```

### 第四步：启动ClaudEditor
```bash
# 方式1：使用全局命令
claudeditor

# 方式2：使用启动脚本
./start_claudeditor_mac.sh

# 方式3：双击桌面快捷方式
# ClaudEditor.app
```

## 🪟 Windows安装

> **注意**: Windows版本正在开发中，预计2025年1月发布。

### 临时解决方案
1. **使用WSL2**:
   ```powershell
   # 安装WSL2
   wsl --install
   
   # 在WSL2中按照Linux步骤安装
   ```

2. **使用Docker**:
   ```powershell
   # 运行Docker容器
   docker run -p 8080:8080 powerautomation/claudeditor:v4.1
   ```

## 🐧 Linux安装

> **注意**: Linux版本正在开发中，预计2025年1月发布。

### 从源码安装
```bash
# 克隆仓库
git clone https://github.com/alexchuang650730/aicore0707.git
cd aicore0707

# 安装依赖
pip3 install -r requirements.txt

# 配置环境
cp config/claudeditor_config.yaml.example config/claudeditor_config.yaml
# 编辑配置文件，添加Claude API密钥

# 启动服务
python3 claudeditor_ui_main.py
```

## 🐳 Docker快速体验

如果您想快速体验PowerAutomation而不进行完整安装：

```bash
# 拉取并运行Docker镜像
docker run -d \
  --name powerautomation \
  -p 8080:8080 \
  -e CLAUDE_API_KEY="your-api-key" \
  powerautomation/claudeditor:v4.1

# 访问Web界面
open http://localhost:8080
```

## 🎯 首次使用

### 1. 验证安装
启动ClaudEditor后，您应该看到：
- ✅ 欢迎界面
- ✅ AI助手聊天窗口
- ✅ 录制控制面板
- ✅ 工具栏和菜单

### 2. 测试AI功能
```python
# 在AI助手中输入
"帮我创建一个简单的Python函数，计算两个数的和"

# AI将生成代码并解释
def add_numbers(a, b):
    """计算两个数的和"""
    return a + b
```

### 3. 尝试录制即测试
1. 点击录制按钮 🔴
2. 在任何应用中进行操作
3. 停止录制 ⏹️
4. 查看生成的测试用例

### 4. 探索工具生态
- **开发工具**: 代码生成、调试、测试
- **协作工具**: 实时编辑、团队沟通
- **生产力工具**: 数据分析、自动化
- **集成工具**: API集成、数据同步
- **安全工具**: 权限管理、安全扫描

## 🎬 功能演示

### 录制即测试演示
```bash
# 启动录制
Cmd+Shift+R  # macOS
Ctrl+Shift+R  # Windows/Linux

# 执行以下操作：
1. 打开浏览器
2. 访问网站
3. 填写表单
4. 点击按钮
5. 验证结果

# 停止录制
Cmd+Shift+S  # macOS
Ctrl+Shift+S  # Windows/Linux

# 查看生成的测试用例
```

### AI代码助手演示
```python
# 在编辑器中输入注释
# 创建一个用户管理系统的API

# AI将自动生成完整的代码结构
from fastapi import FastAPI, HTTPException
from pydantic import BaseModel
from typing import List, Optional

app = FastAPI()

class User(BaseModel):
    id: Optional[int] = None
    name: str
    email: str
    
# ... 完整的API实现
```

## 🔧 常见问题

### Q: 安装失败怎么办？
A: 检查以下几点：
- 确保有管理员权限
- 检查网络连接
- 查看错误日志：`tail -f logs/install.log`

### Q: Claude API连接失败？
A: 验证以下设置：
- API密钥是否正确
- 网络是否能访问api.anthropic.com
- 配置文件格式是否正确

### Q: 录制功能不工作？
A: 可能的原因：
- 需要屏幕录制权限（macOS）
- 防火墙阻止了连接
- 重启应用程序

### Q: 性能问题？
A: 优化建议：
- 增加内存分配
- 关闭不必要的功能
- 使用本地模型（企业版）

## 📚 下一步

### 深入学习
- [📖 完整用户指南](user-guide.md)
- [🤖 AI助手使用指南](ai-assistant.md)
- [🎬 录制即测试教程](record-as-test.md)
- [🛠️ 高级配置指南](advanced-configuration.md)

### 加入社区
- [💬 GitHub Discussions](https://github.com/alexchuang650730/powerautomation_community/discussions)
- [🐛 报告问题](https://github.com/alexchuang650730/powerautomation_community/issues)
- [📧 邮件支持](mailto:support@powerautomation.com)
- [🐦 关注Twitter](https://github.com/alexchuang650730/powerautomation_community/discussions)

### 贡献项目
- [🤝 贡献指南](../CONTRIBUTING.md)
- [🔧 开发者文档](developer-guide.md)
- [🧪 测试指南](testing-guide.md)

## 🎉 恭喜！

您已经成功安装并开始使用PowerAutomation v4.1！

现在您可以：
- ✅ 使用AI助手提升编程效率
- ✅ 录制操作生成自动化测试
- ✅ 利用50+专业工具提升生产力
- ✅ 与团队进行实时协作

**🚀 开始您的AI自动化之旅吧！**

---

*如果您在使用过程中遇到任何问题，请随时通过GitHub Issues或邮件联系我们。我们很乐意帮助您！*

