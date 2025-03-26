# JackProxy - 专业级智能代理池管理系统

JackProxy 是一个企业级高性能代理池管理平台，提供智能代理切换、自动维护和严格的Token授权管理功能。作为网络工程师、安全研究人员和数据科学家的得力助手，JackProxy为各类网络环境提供稳定高效的代理服务。

<div align="center">
  <img src="https://github.com/user-attachments/assets/cc2fed4c-46f1-4730-a5e0-ac9430130671" alt="JackProxy Logo" width="800"/>
  <br/>
  <i>高性能 • 高可用 • 易扩展</i>
</div>

## 🌟 核心优势

- **智能负载均衡** - 先进的负载分配算法确保请求均匀分布于代理池中
- **故障自动转移** - 连接失败时瞬间切换至备用代理，确保业务连续性
- **自愈系统** - 定期自动检测和恢复失效代理，提高资源利用率
- **灵活扩缩容** - 动态管理代理池大小，基于实时需求自动调整资源
- **多层安全防护** - 强健的Token授权机制和细粒度访问控制
- **跨平台兼容** - 完美支持Windows、macOS和Linux系统
- **双层日志架构** - 控制台实时反馈与详细文件日志完美结合

## 🚀 适用场景

JackProxy特别适用于以下专业场景：

- **网络安全研究** - 为渗透测试提供匿名且不断变化的IP地址
- **红蓝对抗演练** - 在攻防实战中实现IP快速切换，逃避检测
- **漏洞赏金平台(SRC)** - 有效规避WAF和频率限制，提高漏洞发现效率
- **数据采集与爬虫** - 绕过反爬机制，实现大规模并发数据获取
- **API密集型应用** - 有效避免请求速率限制，提升API调用稳定性
- **自动化测试** - 模拟不同地理位置的用户请求，进行全面的系统测试
- **市场调研** - 收集不同区域的市场数据，提供全球化的数据支持

## 📋 目录

- [快速开始](#-快速开始)
- [Token授权管理](#-token授权管理)
- [高级代理池功能](#-高级代理池功能)
- [常见问题解答](#-常见问题解答)
- [技术支持](#-技术支持)
- [更新日志](#-更新日志)

## 🚀 快速开始

### 获取与使用

1. **获取授权**
   
   JackProxy目前处于内测阶段，仅通过官方指定渠道提供授权Token。请加入官方微信交流群获取使用授权。关注后台回复【jackproxy】免费🆓获取token
   ![扫码_搜索联合传播样式-白色版](https://github.com/user-attachments/assets/7e00147f-5611-42c4-a40a-3bae0abfebae)


3. **下载客户端**
   
   内测用户可获取适用于Windows、macOS和Linux的预编译二进制文件。
   
   - **从GitHub下载**: 访问项目 [Releases]([https://github.com/jackhou/jackproxy](https://github.com/YingxueSec/JackProxy-Pro/releases) 页面获取最新版本
   - **支持平台**: 
     - Windows (64位)
     - macOS (Intel/AMD64 & Apple Silicon/ARM64)
     - Linux (64位)

4. **启动服务**

   ```bash
   ./jackproxy-pro -token "your-token-here"
   ```

   启动成功后，系统将显示详细的状态信息，包括Token验证状态、代理池统计和服务监听地址。
以下是优化后的版本，采用技术性表述并突出核心优势：

---
**Jackproxy智能代理池技术解析与配套JackProxy-Canip工具说明**

本代理池系统采用动态权重评分机制实现资源最优调度，其核心优势在于：

1. **自适应评分体系**
- 通过机器学习算法对代理节点的响应速度、成功率、并发性能等指标进行多维度评估
- 根据实时表现动态调整节点权重，建立QoS分级模型（A/B/C三级质量评级）

2. **智能调度策略**
- 采用加权轮询算法（Weighted Round Robin），高质量节点获得3-5倍于低质节点的请求概率
- 维持基础轮换机制保障IP隐匿性，同时通过流量倾斜提升整体请求效率

3. **渐进式优化特性**
- 初始阶段采用均匀分布策略（冷启动模式）
- 经过10-15次请求后完成初始数据分析，自动进入智能调度状态
- 系统持续学习，每24小时更新节点评分矩阵

**配套诊断工具功能说明：**
- 实时显示当前代理节点IP及ASN地理信息
- 可视化呈现评分变化曲线与权重分配比例
- 支持手动触发代理切换（强制模式/自动模式）
- 提供历史请求成功率热力图分析

提示：建议通过配套JackProxy-Canip工具观察3-5次请求周期，待系统完成初始学习后即可获得最佳使用体验。
---

## 🔑 Token授权管理

### 使用Token的三种方式

1. **命令行参数**（推荐用于测试）：
   ```bash
   ./jackproxy-pro -token "your-token-here"
   ```

2. **独立文件**（适合敏感环境）：
   创建`token.txt`文件并写入Token：
   ```bash
   4d15ff34030788888888888970ab282
   ```

系统按以下优先级读取Token：命令行参数 > token.txt文件。

### Token授权说明

- JackProxy目前处于内测阶段，Token仅通过官方微信群提供
- 每个Token具有特定的有效期和使用权限
- 请勿将Token分享给未授权用户，违规使用可能导致Token被吊销

## 🔄 高级代理池功能

### 智能代理管理架构

JackProxy采用多层级的代理管理架构，确保代理资源的最优利用：

- **实时健康监控** - 持续评估代理健康状态，自动筛选高质量节点
- **智能轮换机制** - 预防IP被封锁，通过定时轮换确保长期稳定性
- **失效快速恢复** - 基于先进算法自动恢复失效代理，减少资源浪费
- **负载智能分配** - 根据代理响应时间和成功率动态调整负载分配
- **地理位置筛选** - 可配置地理位置筛选规则，满足特定区域访问需求
- **并发控制策略** - 精细化控制每个代理的并发连接数，避免过载

### 自动维护时间表

系统按以下时间表执行自动维护操作：

| 操作 | 频率 | 目的 |
|------|------|------|
| 代理池刷新 | 30分钟 | 保持代理池活跃度 |
| 失效代理恢复 | 2分钟 | 提高资源利用率 |
| 健康状态检查 | 60秒 | 确保代理可用性 |
| 强制代理轮换 | 2分钟 | 防止IP被识别和封锁 |

## ❓ 常见问题解答

### 1. Token相关问题

**Q: 如何获取内测Token？**  
A: 请加入官方微信用户交流群获取内测资格和Token。目前仅接受邀请注册。

**Q: Token过期后如何续期？**  
A: 请联系官方渠道或在微信群中申请Token续期。续期后，只需更新Token即可，无需重新部署系统。

**Q: 如何查看当前Token的详细信息？**  
A: Token信息会在程序启动时显示，包括过期时间和授权类型。

### 2. 代理性能优化

**Q: 如何提高代理稳定性？**  
A: JackProxy已经内置了自动优化算法，通常无需手动调整。如果仍有稳定性问题，请确保网络环境稳定或联系技术支持。

**Q: 代理数量突然减少怎么办？**  
A: 这通常是由于代理质量检测导致的。系统会自动恢复高质量代理，您也可以通过以下方式主动干预：
1. 重启服务获取新的代理池
2. 检查网络连接稳定性
3. 联系技术支持提供帮助

### 3. 日志与监控

**Q: 如何优化日志以节省磁盘空间？**  
A: 可以通过配置文件禁用文件日志或调高日志级别。具体设置方法请参考内测文档或咨询技术支持。

**Q: 如何监控代理池健康状态？**  
A: JackProxy提供多种方式监控系统健康状态：
1. 控制台实时显示代理池统计信息
2. 日志文件记录详细的代理状态变化

## 📞 技术支持

如遇问题或需要技术支持，请通过以下渠道联系我们：

- **微信用户交流群**：请扫描官方二维码加入
- **GitHub Issue**：[提交问题](https://github.com/your-repo/issues)
- **邮件支持**：jackh0u@qq.com

## 📝 更新日志

### v3.8.0 (2025-03-26)

- **🔥 新功能**: 全新日志管理系统
  - 增加文件日志开关控制，可完全禁用文件日志降低I/O占用
  - 智能UI适配，根据配置动态显示日志状态
  - 优化启动消息流程，提供更清晰的系统状态反馈

### v3.7.0 (2025-03-25)

- **🛠️ 架构升级**: 日志系统全面重构
  - 实现组件级日志隔离，可单独控制Token验证、API调用日志级别
  - 优化标准库日志重定向，防止日志信息混淆
  - 智能控制台过滤，根据重要性动态调整显示内容

### v3.6.0 (2025-03-23)

- **🚀 性能优化**: 代理池管理引擎升级
  - 新增启动时初始代理获取控制，支持灵活的代理初始化策略
  - 优化代理池初始化逻辑，支持完全静态代理池模式
  - 重构代理获取流程，降低系统负载提高响应速度

### v3.5.0 (2025-03-21)

- **⚙️ 增强配置**: 高级代理更新控制
  - 引入细粒度代理更新策略控制参数
  - 支持定制化的代理刷新行为
  - 优化资源利用效率，提高系统稳定性

### v3.4.0 (2025-03-20)

- **🧠 智能升级**: 代理测试策略革新
  - 采用AI驱动的代理质量评估系统
  - 实现更精准的代理冷却期管理
  - 引入代理生命周期管理，显著提升代理池质量

### v3.3.0 (2025-03-17)

- **⚡ 启动优化**: 极速启动与Token管理
  - 优化启动流程，显著提升启动速度
  - 增强Token验证机制，支持多种Token获取方式
  - 改进代理测试逻辑，确保代理池高可用性

### v3.2.0 (2025-03-15)

- **🔒 安全增强**: 多层授权与高级代理切换
  - 实现基于文件的Token管理系统
  - 优化Token验证流程，支持自动续期
  - 增强代理轮换机制，提高匿名性和安全性

### v3.1.0 (2025-03-05)

- **🌐 核心升级**: 智能代理管理
  - 首次引入自动代理恢复系统
  - 实现基于响应时间的智能代理选择
  - 优化代理池自动维护机制，提高系统整体稳定性

---

<div align="center">
  <p>JackProxy © 2023 - 专业的代理管理解决方案</p>
  <p>
    <small>本软件为闭源商业软件，未经授权不得复制、分发或修改</small>
  </p>
</div> 
