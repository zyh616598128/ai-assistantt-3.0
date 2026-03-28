# AI E-Commerce Assistant

[![Java](https://img.shields.io/badge/Java-17+-007396.svg)](https://openjdk.java.net)
[![Spring Boot](https://img.shields.io/badge/Spring_Boot-3.0+-6DB33F.svg)](https://spring.io/projects/spring-boot)
[![Vue.js](https://img.shields.io/badge/Vue.js-3+-4FC08D.svg)](https://vuejs.org)
[![Maven](https://img.shields.io/badge/Maven-3.8+-C71A36.svg)](https://maven.apache.org)

> 基于AI的电商智能助手平台，提供产品分析、价格优化、库存管理、客户洞察等全方位电商运营支持。

## 🌟 项目概述

AI E-Commerce Assistant 是一个集成多种AI能力的电商智能运营平台，通过机器学习算法和大数据分析，为电商企业提供数据驱动的决策支持和自动化运营工具。

### ✨ 核心功能

- **🤖 AI产品分析**: 智能分析产品竞争力、市场定位、优化建议
- **💰 动态定价策略**: 基于市场供需、竞品价格的智能调价
- **📦 库存智能管理**: 预测需求、优化库存、降低滞销风险
- **👥 客户画像分析**: 深度分析客户行为、偏好、购买模式
- **📈 销售预测**: 基于历史数据的销量预测和趋势分析
- **🎯 营销活动优化**: AI驱动的精准营销和内容推荐
- **⚠️ 异常检测**: 实时监控订单、库存、价格的异常情况
- **📊 可视化报表**: 直观的数据展示和业务洞察

## 🏗️ 技术架构

### 后端技术栈
- **API框架**: Spring Boot 3.0+ (Java 17+)
- **构建工具**: Maven 3.8+
- **AI/ML库**: Deeplearning4j, Weka, Apache Commons Math
- **数据库**: PostgreSQL 13+ + Redis缓存
- **消息队列**: Spring Kafka + Redis
- **搜索引擎**: Elasticsearch 8.x
- **认证授权**: Spring Security + JWT + OAuth2
- **容器化**: Docker + Docker Compose
- **ORM框架**: Spring Data JPA + Hibernate
- **API文档**: Springdoc OpenAPI 2.0

### 前端技术栈
- **框架**: Vue.js 3 + Composition API
- **UI组件库**: Element Plus
- **状态管理**: Pinia
- **路由**: Vue Router 4
- **构建工具**: Vite
- **图表库**: ECharts
- **HTTP客户端**: Axios

### AI模型集成
- **NLP处理**: 文本分析、情感分析、关键词提取
- **计算机视觉**: 产品图片分析、品牌识别
- **推荐系统**: 协同过滤、内容推荐
- **时间序列**: 销量预测、价格趋势分析

## 📁 项目结构

```
ai-ecommerce-assistant/
├── src/
│   ├── backend/                 # Python FastAPI 后端
│   │   ├── app/
│   │   │   ├── api/             # API路由
│   │   │   ├── core/             # 核心配置
│   │   │   ├── models/           # 数据模型
│   │   │   ├── schemas/          # Pydantic模型
│   │   │   ├── services/         # 业务服务
│   │   │   ├── ai/              # AI模型服务
│   │   │   ├── utils/            # 工具函数
│   │   │   └── main.py           # 应用入口
│   │   ├── requirements.txt
│   │   └── Dockerfile
│   └── frontend/                # Vue.js 前端
│       ├── src/
│       │   ├── components/       # UI组件
│       │   ├── views/            # 页面视图
│       │   ├── stores/           # Pinia状态
│       │   ├── router/           # 路由配置
│       │   ├── services/         # API服务
│       │   ├── utils/            # 工具函数
│       │   └── App.vue
│       ├── package.json
│       └── Dockerfile
├── docs/                        # 项目文档
│   ├── api/                     # API文档
│   ├── deployment/              # 部署指南
│   └── development/             # 开发指南
├── scripts/                     # 部署脚本
├── docker/                      # Docker配置
│   ├── docker-compose.yml
│   └── nginx.conf
├── tests/                       # 测试文件
│   ├── unit/                    # 单元测试
│   ├── integration/             # 集成测试
│   └── e2e/                     # 端到端测试
├── deployment/                  # 生产部署
│   ├── kubernetes/              # K8s配置
│   └── terraform/               # 基础设施代码
└── README.md                    # 项目说明
```

## 🚀 快速开始

### 环境要求

- **Java**: 17+
- **Maven**: 3.8+
- **Node.js**: 18+
- **PostgreSQL**: 13+
- **Redis**: 6+
- **Docker**: 20.10+

### 1. 克隆项目

```bash
git clone <repository-url>
cd ai-ecommerce-assistant
```

### 2. 后端设置

```bash
cd src/backend

# 编译项目
mvn clean compile

# 配置环境变量
cp application.yml.example application.yml
# 编辑 application.yml 文件，填入配置信息

# 启动开发服务器
mvn spring-boot:run

# 或使用Java命令启动
java -jar target/ai-ecommerce-assistant-1.0.0.jar
```

### 3. 前端设置

```bash
cd src/frontend

# 安装依赖
npm install

# 配置环境变量
cp .env.example .env.local
# 编辑 .env.local 文件

# 启动开发服务器
npm run dev
```

### 4. Docker部署（推荐）

```bash
# 启动所有服务
docker-compose up -d

# 查看服务状态
docker-compose ps

# 查看日志
docker-compose logs -f
```

## 📚 API文档

启动后端服务后，访问以下地址：
- **Swagger UI**: http://localhost:8000/docs
- **ReDoc**: http://localhost:8000/redoc
- **OpenAPI JSON**: http://localhost:8000/openapi.json

### 主要API端点

#### 产品分析 API
```http
POST /api/v1/products/analyze
Content-Type: application/json

{
  "product_id": "prod_001",
  "product_data": {
    "title": "无线蓝牙耳机",
    "price": 299.99,
    "category": "电子产品",
    "images": ["url1", "url2"],
    "description": "高品质无线耳机..."
  },
  "marketplace": "amazon",
  "analysis_type": ["competitiveness", "optimization"]
}
```

#### 定价建议 API
```http
POST /api/v1/pricing/suggest
Content-Type: application/json

{
  "product_id": "prod_001",
  "current_price": 299.99,
  "target_margin": 0.3,
  "competitor_prices": [289.99, 315.00, 275.50],
  "demand_indicators": {
    "seasonality": 0.8,
    "trend": "increasing"
  }
}
```

#### 库存预测 API
```http
POST /api/v1/inventory/forecast
Content-Type: application/json

{
  "product_id": "prod_001",
  "historical_sales": [...],
  "lead_time": 7,
  "safety_stock_days": 14,
  "promotion_plans": []
}
```

## 🔧 配置说明

### 环境变量

| 变量名 | 描述 | 示例值 |
|--------|------|--------|
| `DATABASE_URL` | 数据库连接 | `postgresql://user:pass@localhost/db` |
| `REDIS_URL` | Redis连接 | `redis://localhost:6379/0` |
| `SECRET_KEY` | JWT密钥 | `your-secret-key` |
| `OPENAI_API_KEY` | OpenAI API密钥 | `sk-...` |
| `AMAZON_API_KEY` | Amazon API密钥 | `amzn_...` |
| `LOG_LEVEL` | 日志级别 | `INFO` |

### AI模型配置

主要AI模型配置文件：`src/backend/app/core/config.py`

```python
AI_MODELS = {
    "sentiment_analysis": {
        "model_name": "cardiffnlp/twitter-roberta-base-sentiment-latest",
        "max_length": 512
    },
    "price_prediction": {
        "algorithm": "random_forest",
        "features": ["historical_price", "competitor_price", "demand"]
    }
}
```

## 📊 功能模块详解

### 1. 产品分析模块
- **竞争力评估**: 基于价格、评价、销量的综合评分
- **优化建议**: 标题、描述、图片、定价的改进建议
- **市场定位**: 目标客群、差异化优势分析
- **生命周期管理**: 新品推广、成熟期维护、衰退期处理

### 2. 智能定价模块
- **动态调价**: 基于竞品、库存、需求的实时调整
- **促销策略**: 最优折扣力度和时间点计算
- **价格弹性**: 需求对价格变化的敏感度分析
- **利润最大化**: 在销量和利润率间寻找平衡点

### 3. 库存管理模块
- **需求预测**: 基于时间序列分析的销量预测
- **补货建议**: 最优订购量和时机计算
- **滞销预警**: 识别可能滞销的商品
- **多仓库协调**: 库存调配和优化

### 4. 客户分析模块
- **画像构建**: 年龄、性别、消费习惯分析
- **行为预测**: 购买概率、流失风险预测
- **细分群组**: RFM分析、聚类分组
- **个性化推荐**: 基于协同过滤的内容推荐

## 🧪 测试

### 单元测试
```bash
cd src/backend
mvn test

cd src/frontend
npm run test:unit
```

### 集成测试
```bash
cd src/backend
mvn verify -Pintegration-test
```

### E2E测试
```bash
cd src/frontend
npm run test:e2e
```

## 📈 性能优化

- **缓存策略**: Redis多层缓存热点数据
- **数据库优化**: 索引设计、查询优化、分库分表
- **异步处理**: Celery处理耗时AI推理任务
- **CDN加速**: 静态资源和图片CDN分发
- **负载均衡**: Nginx反向代理和负载均衡

## 🔒 安全特性

- **身份认证**: JWT Token + OAuth2.0
- **访问控制**: 基于角色的权限管理(RBAC)
- **数据加密**: AES-256传输和存储加密
- **API保护**: 限流、防刷、SQL注入防护
- **审计日志**: 关键操作日志记录

## 🚢 部署指南

### Docker部署

```yaml
# docker-compose.yml 示例
version: '3.8'
services:
  backend:
    build: ./src/backend
    ports:
      - "8000:8000"
    environment:
      - DATABASE_URL=postgresql://postgres:pass@db:5432/ecommerce
    depends_on:
      - db
      - redis
  
  frontend:
    build: ./src/frontend
    ports:
      - "3000:3000"
    depends_on:
      - backend
  
  db:
    image: postgres:13
    environment:
      POSTGRES_DB: ecommerce
      POSTGRES_PASSWORD: pass
    volumes:
      - postgres_data:/var/lib/postgresql/data
  
  redis:
    image: redis:6-alpine

volumes:
  postgres_data:
```

### Kubernetes部署

生产级K8s配置位于 `deployment/kubernetes/`

```bash
# 部署到K8s
kubectl apply -f deployment/kubernetes/
```

## 🤝 贡献指南

欢迎提交Issue和Pull Request！

### 开发流程
1. Fork 本仓库
2. 创建特性分支 (`git checkout -b feature/amazing-feature`)
3. 提交更改 (`git commit -m 'Add amazing feature'`)
4. 推送分支 (`git push origin feature/amazing-feature`)
5. 创建 Pull Request

### 代码规范
- Python: 遵循 PEP 8
- JavaScript: ESLint + Prettier
- Git: Conventional Commits
- 测试覆盖率 > 80%

## 📄 许可证

本项目采用 MIT 许可证 - 详见 [LICENSE](LICENSE) 文件。

## 🙏 致谢

感谢以下开源项目和技术：
- FastAPI - 现代Python API框架
- Vue.js - 渐进式JavaScript框架
- scikit-learn - 机器学习库
- Element Plus - Vue组件库
- Docker - 容器化平台

## 📞 联系方式

- **项目主页**: https://github.com/your-username/ai-ecommerce-assistant
- **问题反馈**: https://github.com/your-username/ai-ecommerce-assistant/issues
- **邮箱联系**: support@aiecommerce.com
- **技术交流**: Discord服务器链接

---

⭐ 如果这个项目对您有帮助，请给我们一个星标！