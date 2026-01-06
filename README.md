# 研学教育实践课程开发工具

一个功能完整的研学教育实践课程开发SaaS平台，支持课程开发、AI辅助、审核发布等功能。

## 功能特性

### 用户管理
- 用户注册和登录
- 基于角色的权限控制（RBAC）
- 支持管理员、教师、学生三种角色

### 课程管理
- 课程创建、编辑、删除
- 课程内容管理（文本、图片、视频、文档等）
- 课程版本控制
- 课程搜索和筛选

### AI服务集成
- 百度OCR图文识别
- DeepSeek智能内容生成
- 豆包AI助手
- KIMI AI服务
- 服务降级机制

### 审核发布流程
- 多级审核流程
- 审核记录追踪
- 版本管理
- 发布控制

### 手册生成
- HTML格式导出
- PDF格式导出
- 自定义模板

### API配置管理
- 第三方服务凭证管理
- 服务启用/禁用控制
- 安全存储

## 技术栈

### 后端
- Nest.js
- TypeORM
- PostgreSQL/SQLite
- JWT认证
- Multer文件上传

### 前端
- React 19
- TypeScript
- Vite
- Material-UI (MUI v7)
- Zustand状态管理
- Formik表单处理
- Recharts数据可视化

## 快速开始

### 安装依赖

```bash
# 后端
npm install

# 前端
cd frontend
npm install
```

### 配置环境变量

复制 `.env.example` 到 `.env` 并配置以下变量：

```env
# Database Configuration
USE_MEMORY_DB=true
DB_HOST=localhost
DB_PORT=5432
DB_USERNAME=postgres
DB_PASSWORD=password
DB_NAME=stp_db
DB_SYNCHRONIZE=true

# JWT Configuration
JWT_SECRET=your-secret-key
JWT_EXPIRATION_TIME=3600

# Server Configuration
PORT=3000
NODE_ENV=development
```

### 初始化数据库

```bash
npm run init-db
```

### 启动开发服务器

```bash
# 后端（终端1）
npm run start:dev

# 前端（终端2）
cd frontend
npm run dev
```

### 访问应用

- 前端：http://localhost:5173
- 后端API：http://localhost:3000

### 测试账号

- 管理员：admin / admin123
- 教师：teacher / teacher123
- 学生：student / student123

## 项目结构

```
stP/
├── src/                    # 后端源代码
│   ├── entities/           # 数据库实体
│   ├── auth/              # 认证模块
│   ├── user/              # 用户管理
│   ├── role/              # 角色管理
│   ├── permission/         # 权限管理
│   ├── course/            # 课程管理
│   ├── api-config/        # API配置
│   └── ai-service/        # AI服务
├── frontend/              # 前端源代码
│   ├── src/
│   │   ├── pages/         # 页面组件
│   │   ├── components/    # 通用组件
│   │   ├── services/      # API服务
│   │   ├── store/         # 状态管理
│   │   └── types/         # TypeScript类型
│   └── dist/             # 构建输出
├── uploads/               # 上传文件存储
├── manuals/              # 生成的手册
└── test-data.db          # SQLite数据库文件
```

## 部署

详细的部署指南请参考 [DEPLOYMENT_GUIDE.md](./DEPLOYMENT_GUIDE.md)

### 快速部署

```bash
# 构建前端
cd frontend
npm run build

# 构建后端
cd ..
npm run build

# 启动生产服务器
node dist/main.js
```

## 开发

### 运行测试

```bash
npm test
```

### 代码规范

```bash
npm run lint
```

## 贡献

欢迎提交Issue和Pull Request！

## 许可证

MIT License
