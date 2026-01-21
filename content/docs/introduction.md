---
title: "项目介绍"
date: 2026-01-21
weight: 2
---

# Financial Manager 项目信息

基于Spring Boot的个人投资组合管理系统，支持多组合管理、交易记录、持仓分析、价格更新、Git自动同步、收益曲线图表展示和网格交易条件单系统。

## 核心功能

- **多组合投资追踪管理**
- **交易历史记录** (买入/卖出/入金/出金/分红)
- **实时持仓分析和盈亏计算**
- **外部API自动价格更新**
- **网格交易条件单系统**
- **基于Git的备份和版本控制**
- **Chart.js交互式收益曲线**
- **Web通知系统**
- **原生macOS桌面应用支持**

## 技术栈

- **框架**: Spring Boot 3.5.5 + Java 21
- **Web层**: Thymeleaf模板 + Spring MVC控制器
- **数据存储**: Excel文件 (Apache POI) + 自定义 `@ExcelColumn` 注解映射
- **Git集成**: JGit自动同步到远程仓库 (Gitee)
- **桌面应用**: jpackage打包原生macOS应用
- **前端**: Chart.js交互式收益曲线
- **HTTP客户端**: RestTemplate外部API集成
- **构建工具**: Maven
- **服务端口**: 8080

## 系统架构概览

### 核心架构模式
这是一个**基于Excel文件持久化的Spring Boot Web应用**，采用分层架构，并集成了事件驱动的网格交易条件单系统：

```
Web层 (控制器) → 服务层 → 领域层 → Excel文件
                              ↓
                        Git仓库 (备份)

事件驱动架构 (网格交易):
价格更新 → PriceUpdateEvent → 异步触发检查 → 通知系统
```

### 关键架构决策

1. **Excel文件持久化**: 不使用传统数据库，所有数据存储在Excel文件中，通过Apache POI和自定义`@ExcelColumn`注解进行字段映射。
2. **Git集成**: Excel文件通过`GitService`自动同步到远程Git仓库(Gitee)进行备份和版本控制。
3. **双应用模式**:
   - Web应用 (`Application.java`) - 标准Spring Boot应用
   - 桌面应用 (`DesktopApplication.java`) - 打包为原生macOS应用
4. **通知系统**: 基于Web的通知系统，使用`NotificationService`为用户提供操作反馈和Git同步状态。
5. **数据一致性**: 交易重放系统用于数据完整性验证

