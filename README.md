# 智能购物助手

这是一个基于Docker的智能购物助手应用，集成了Next.js前端、后端API和Nginx服务器。

## 项目架构

该项目由三个主要组件组成：

1. **前端应用** - 基于Next.js构建的用户界面
2. **后端服务** - 提供API支持的后端应用
3. **Nginx服务器** - 作为反向代理，处理请求路由和负载均衡

## 快速开始

### 前提条件

- 安装 [Docker](https://www.docker.com/get-started)
- 安装 [Docker Compose](https://docs.docker.com/compose/install/)

### 部署步骤

1. 克隆此仓库到本地：

```bash
git clone <仓库URL>
cd deploy
```

2. 启动应用：

```bash
docker-compose up -d
```

3. 访问应用：

打开浏览器，访问 `http://localhost`

### 停止应用

```bash
docker-compose down
```

## 服务说明

### Nginx

- 端口映射：80:80
- 作为反向代理服务器，将请求路由到前端和后端服务

### 前端应用 (Next.js)

- 容器名称：next-frontend
- 内部端口：3000
- 镜像：murphyz1024/smart-shopping-app
- 提供用户界面和交互功能

### 后端服务

- 容器名称：backend-app
- 内部端口：5005
- 镜像：cloudsmithy/shoppingassistant-backend
- 提供API和业务逻辑处理

## 配置说明

可以通过修改 `docker-compose.yml` 文件来调整服务配置，如端口映射、环境变量等。

## 维护与更新

更新服务镜像：

```bash
docker-compose pull
docker-compose up -d
```

## 故障排除

如果遇到问题，可以查看容器日志：

```bash
# 查看所有容器日志
docker-compose logs

# 查看特定服务日志
docker-compose logs nginx
docker-compose logs next-app
docker-compose logs backend
```

## 许可证

[添加许可证信息]