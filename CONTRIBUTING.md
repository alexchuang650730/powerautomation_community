# 🤝 贡献指南

感谢您对PowerAutomation v4.1的关注！我们欢迎所有形式的贡献，无论是代码、文档、bug报告还是功能建议。

## 🌟 贡献方式

### 1. ⭐ Star项目
最简单的支持方式就是给项目一个Star！这能帮助更多人发现PowerAutomation。

### 2. 🐛 报告Bug
发现问题？请通过[GitHub Issues](https://github.com/alexchuang650730/powerautomation_community/issues)报告：
- 使用Bug报告模板
- 提供详细的复现步骤
- 包含环境信息和错误日志

### 3. 💡 功能建议
有好想法？我们很乐意听到：
- 使用功能请求模板
- 详细描述使用场景
- 说明功能的价值和优先级

### 4. 📚 改进文档
文档永远可以更好：
- 修正错别字和语法错误
- 添加使用示例
- 翻译成其他语言
- 改进API文档

### 5. 🔧 贡献代码
想要直接贡献代码？太棒了！

## 🚀 开发环境设置

### 前置要求
- Python 3.8+
- Node.js 16+
- Git
- Claude API密钥

### 本地开发设置

```bash
# 1. Fork并克隆仓库
git clone https://github.com/YOUR_USERNAME/powerautomation_community.git
cd powerautomation_community

# 2. 设置上游仓库
git remote add upstream https://github.com/alexchuang650730/powerautomation_community.git

# 3. 创建虚拟环境
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# 4. 安装依赖
pip install -r requirements.txt
npm install

# 5. 配置环境变量
cp .env.example .env
# 编辑.env文件，添加您的Claude API密钥

# 6. 运行测试
python -m pytest tests/
npm test

# 7. 启动开发服务器
python claudeditor_ui_main.py
```

## 📋 开发流程

### 1. 创建分支
```bash
# 从main分支创建新分支
git checkout main
git pull upstream main
git checkout -b feature/your-feature-name
```

### 2. 开发和测试
- 编写代码
- 添加测试
- 确保所有测试通过
- 遵循代码规范

### 3. 提交代码
```bash
# 提交更改
git add .
git commit -m "feat: 添加新功能描述"

# 推送到您的fork
git push origin feature/your-feature-name
```

### 4. 创建Pull Request
- 在GitHub上创建Pull Request
- 填写PR模板
- 等待代码审查

## 📝 代码规范

### Python代码规范
- 遵循PEP 8
- 使用类型提示
- 编写文档字符串
- 保持函数简洁

```python
def process_data(data: List[Dict[str, Any]]) -> Dict[str, int]:
    """
    处理数据并返回统计信息。
    
    Args:
        data: 输入数据列表
        
    Returns:
        包含统计信息的字典
    """
    # 实现代码
    pass
```

### JavaScript代码规范
- 使用ES6+语法
- 遵循ESLint规则
- 编写JSDoc注释

### 提交信息规范
使用[Conventional Commits](https://www.conventionalcommits.org/)格式：

```
type(scope): description

[optional body]

[optional footer]
```

类型：
- `feat`: 新功能
- `fix`: Bug修复
- `docs`: 文档更新
- `style`: 代码格式化
- `refactor`: 代码重构
- `test`: 测试相关
- `chore`: 构建过程或辅助工具的变动

示例：
```
feat(record-as-test): 添加智能操作识别功能

- 实现基于AI的用户操作识别
- 支持复杂UI交互的自动化识别
- 添加操作验证和优化机制

Closes #123
```

## 🧪 测试指南

### 运行测试
```bash
# 运行所有测试
python -m pytest

# 运行特定测试文件
python -m pytest tests/test_record_as_test.py

# 运行带覆盖率的测试
python -m pytest --cov=core tests/

# 运行前端测试
npm test
```

### 编写测试
- 为新功能编写单元测试
- 为API编写集成测试
- 为UI功能编写端到端测试

## 📖 文档贡献

### 文档结构
```
docs/
├── quick-start.md          # 快速开始
├── installation.md         # 安装指南
├── api-reference.md        # API文档
├── architecture.md         # 架构文档
└── claude-code/           # Claude Code专题
    ├── page-1-overview.md
    ├── page-2-usage.md
    └── page-3-best-practices.md
```

### 文档规范
- 使用Markdown格式
- 包含代码示例
- 添加截图和图表
- 保持内容更新

## 🏷️ 标签和里程碑

### Issue标签
- `bug`: Bug报告
- `enhancement`: 功能增强
- `documentation`: 文档相关
- `good first issue`: 适合新贡献者
- `help wanted`: 需要帮助
- `priority/high`: 高优先级
- `priority/medium`: 中优先级
- `priority/low`: 低优先级

### 里程碑
- `v4.1.1`: Bug修复版本
- `v4.2.0`: 功能增强版本
- `v5.0.0`: 重大版本更新

## 🎯 贡献者认可

### 贡献者等级
- **🌟 Star Contributor**: 首次贡献
- **🚀 Active Contributor**: 多次贡献
- **💎 Core Contributor**: 核心贡献者
- **👑 Maintainer**: 项目维护者

### 认可方式
- 在README中列出贡献者
- 发放贡献者徽章
- 邀请加入核心团队
- 提供技术指导机会

## 📞 获取帮助

### 联系方式
- **GitHub Discussions**: [技术讨论](https://github.com/alexchuang650730/powerautomation_community/discussions)
- **GitHub Issues**: [问题报告](https://github.com/alexchuang650730/powerautomation_community/issues)
- **邮箱**: contribute@gmail.com
- **微信群**: 扫码加入开发者群

### 开发者资源
- [架构文档](docs/architecture.md)
- [API文档](docs/api-reference.md)
- [开发者指南](docs/developer-guide.md)
- [常见问题](docs/faq.md)

## 🙏 致谢

感谢所有为PowerAutomation做出贡献的开发者！

### 核心贡献者
- [@alexchuang650730](https://github.com/alexchuang650730) - 项目创始人
- 更多贡献者正在加入...

### 特别感谢
- Anthropic团队 - Claude AI技术支持
- 开源社区 - 各种优秀的开源项目
- 早期用户 - 宝贵的反馈和建议

---

**🚀 让我们一起构建AI自动化的未来！**

*每一个贡献都很重要，无论大小。感谢您成为PowerAutomation社区的一员！*

