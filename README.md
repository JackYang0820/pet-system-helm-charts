# Pet System Helm Charts

集中管理虚拟宠物养成系统的所有 Kubernetes 部署配置。

## 包含的服务

| Chart | 服务 | 说明 |
|-------|------|------|
| userserver-chart | 用户认证服务 | JWT 登录/注册 |
| gameserver-chart | 游戏服务 | 游戏逻辑处理 |
| petengine-chart | 宠物引擎 | 宠物状态管理 |
| backupserver-chart | 备份服务 | 数据备份 |
| health-chart | 健康检查 | AWS ELB 健康检查探活 |
| ingress-chart | 路由规则 | Ingress 配置 |

## 快速部署

```bash
# 创建命名空间
kubectl create namespace jack

# 部署用户服务
helm upgrade --install userserver ./charts/userserver-chart -n jack

# 部署游戏服务
helm upgrade --install gameserver ./charts/gameserver-chart -n jack

# 部署宠物引擎
helm upgrade --install petengine ./charts/petengine-chart -n jack

# 部署备份服务
helm upgrade --install backupserver ./charts/backupserver-chart -n jack

# 部署健康检查
helm upgrade --install health ./charts/health-chart -n jack

# 部署 Ingress 路由
helm upgrade --install ingress ./charts/ingress-chart -n jack
