<p align="center">
  <img src="https://via.placeholder.com/200x60/1a237e/ffffff?text=HnuSec+Spring" alt="HnuSec Logo" width="200">
  <br>
  <img src="https://img.shields.io/github/last-commit/HnuSec/HnuSec-spring-train?style=flat-square&color=2196F3">
  <img src="https://img.shields.io/badge/Spring%20Boot-2.7.4-brightgreen?style=flat-square&logo=spring">
  <img src="https://img.shields.io/badge/license-Apache--2.0-important?style=flat-square">
</p>

<h1 align="center">🚩 HnuSec 春季培训作业系统</h1>

> 「网络安全实战训练平台 · 2024春季学期专用」

## 🌟 平台亮点

| ​**功能特性**​               | ​**技术实现**​                          | ​**安全防护**​                 |
|---------------------------|--------------------------------------|----------------------------|
| 🛡️ 双因子认证              | Spring Security + JWT               | 请求签名校验                 |
| 📦 作业自动查重            | SimHash算法 + Elasticsearch         | 防重放攻击机制               |
| 📊 实时排行榜              | Redis SortedSet + 定时持久化         | SQL注入过滤层               |
| 📝 Markdown提交            | Editor.md + XSS过滤                  | 文件类型白名单               |
| 📈 训练进度可视化           | ECharts + 数据脱敏处理               | 访问频率限制                |

## 🛠️ 快速部署

### 环境要求
```bash
JDK 17+ | MySQL 8.0+ | Redis 6.0+ | Elasticsearch 7.17
