# Agent团队协作开发指南

## 团队架构

### 核心成员配置
- **01-engine-agent.md**: 引擎开发总监Agent - 负责Godot引擎功能扩展和优化
- **02-mcp-agent.md**: MCP Tools项目总监Agent - 负责Godot-MCP工具链开发和维护  
- **03-game-agent.md**: FlappyBirdDemo项目总监Agent - 负责游戏开发测试和验证
- **04-manager-agent.md**: 团队项目经理Agent - 负责项目协调和文档管理

### 技术架构
```
Claude AI ↔ MCP Server ↔ Godot Editor ↔ Godot Engine ↔ Game Projects
```

## 项目仓库

### GitHub仓库地址
- **Common**: https://github.com/hbs08219/Common.git - 团队共享文档和配置
- **Godot引擎**: https://github.com/hbs08219/godot.git - Godot引擎源码（fork自官方）
- **Godot-MCP**: https://github.com/hbs08219/Godot-MCP.git - MCP工具链项目
- **FlappyBirdDemo**: https://github.com/hbs08219/flappybirddemo.git - 游戏测试项目

## 快速部署

### 环境要求
- 操作系统: Windows 10/11, macOS 10.15+, Ubuntu 18.04+
- 内存: 8GB+, 推荐16GB+
- 开发工具: Node.js 18.x+, Git, Python 3.8+

### 部署步骤
```bash
# 1. Godot引擎源码
git clone https://github.com/hbs08219/godot.git godot_source
cd godot_source
git checkout 4.2-stable
scons platform=windows target=editor

# 2. Godot-MCP工具
git clone https://github.com/hbs08219/Godot-MCP.git Godot-MCP
cd Godot-MCP/server
npm install && npm run build

# 3. 插件安装
# 复制 addons/godot_mcp 到Godot项目的 addons 目录
# 在Godot中启用 "Godot MCP" 插件
```

## 协作流程

### 开发阶段
1. **需求分析**: 项目经理收集需求，各Agent分析技术可行性
2. **方案设计**: 协作设计整体解决方案，确定接口规范
3. **并行开发**: 各Agent在专业领域并行开发，通过MCP工具协作
4. **测试验证**: 功能测试、集成测试、用户体验测试
5. **部署发布**: 代码审查、构建打包、部署验证

### 沟通机制
- **实时协作**: 通过MCP工具进行实时协作
- **定期会议**: 每日站会、每周评审、每月总结
- **文档共享**: 维护统一技术文档库，及时更新项目状态

## 质量保证

### 代码质量
- 遵循编码规范，进行代码审查，建立自动化测试
- 单元测试覆盖率不低于80%
- 集成测试覆盖主要功能流程

### 流程质量
- 标准化工作流程，持续监控和改进
- 定期评估流程效果，收集改进建议

## 快速检查清单

### 部署验证
- [ ] MCP服务器正常启动
- [ ] Claude能够连接Godot
- [ ] 基本命令执行成功
- [ ] 游戏项目正常运行

### 常见问题
- **连接失败**: 检查WebSocket服务器状态，验证配置文件
- **命令执行失败**: 查看Godot控制台和MCP服务器日志
- **插件不工作**: 确认插件已启用，检查项目设置

## 维护信息

- **文档维护**: 团队项目经理Agent
- **技术审核**: 各专业Agent总监
- **更新频率**: 根据项目进展定期更新
- **反馈渠道**: 通过MCP工具或项目管理系统

---

**文档版本**: 1.0  
**最后更新**: 2025-01-14  
**维护人员**: 团队项目经理Agent
