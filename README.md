# myAdmin

一个基于 Vue3 + Node 的企业后台管理系统模板。

## 技术栈

**前端**
- Vue3 + Vite
- Element Plus
- Vue Router 4
- Pinia
- Axios
- ECharts

**后端**
- Node + Express
- SQLite（开发）/ PostgreSQL（部署）
- JWT 认证
- bcrypt 密码加密

## 功能

- [x] 登录 / 注册（JWT）
- [ ] 用户管理（增删改查）
- [ ] 角色权限（管理员 / 普通用户）
- [ ] 菜单管理（动态渲染）
- [ ] 数据看板（ECharts 图表）

## 当前版本不包含（架构已预留）

以下功能在 v1.0 不实现，但数据库和代码结构已预留扩展点：

- 多租户 SaaS（users 表预留 `tenant_id`）
- 工作流引擎（users 表预留 `status`）
- 文件存储 / CDN（`avatar` 字段存 URL）
- 国际化（文案集中管理）
- 移动端（接口返回纯数据）
- 行列级数据权限（查询统一封装在 `db/queries.js`）

## 目录结构

myAdmin/
├── client/                 # 前端
│   └── src/
│       ├── api/            # 接口封装
│       ├── router/         # 路由 + 守卫
│       ├── stores/         # Pinia
│       └── views/          # 页面
├── server/                 # 后端
│   └── src/
│       ├── db/             # 数据库连接 + 查询封装
│       ├── middlewares/    # 中间件
│       ├── routes/         # 路由
│       └── app.js
├── scripts/                # 推送脚本
├── docs/                   # 文档
└── README.md

## 本地启动

### 后端

cd server
npm install
npm run dev

访问 http://localhost:3000

### 前端

cd client
npm install
npm run dev

访问 http://localhost:5173

## 环境变量

### 后端（server/.env）

复制 server/.env.example 为 server/.env，填写：

PORT=3000
JWT_SECRET=your-secret-here
JWT_EXPIRES_IN=1d
DB_PATH=./data/myadmin.db
NODE_ENV=development

### 前端

- client/.env.development：VITE_API_BASE=http://localhost:3000/api
- client/.env.production：VITE_API_BASE=https://your-app.railway.app/api

## 推送

推 GitHub：

git push origin main

推 Gitee：

git push gitee main

## 版本规划

- v1.0：认证闭环（登录 / 注册 / JWT）
- v1.1：用户管理 CRUD
- v1.2：角色权限
- v1.3：菜单管理
- v2.0：数据看板