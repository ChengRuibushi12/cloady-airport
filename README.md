# Cloady 免费容器节点部署套件

本套件为 **Cloady (cloady.com)** 免费容器平台（0.5 vCPU / 1GB RAM / 200GB 免费月流量）定制构建，内置 Xray-core 核心与轻量化 Node.js 调度器，支持 WebSocket + TLS 全加密传输，提供原生 Web 面板与 Clash 订阅直连。

---

## 包含文件清单

- `Dockerfile`: 基于 Alpine 构建的超轻量镜像（内存占用仅 ~25MB），自动获取最新版 Xray-core。
- `docker-compose.yml`: Cloady 优先识别的编排配置。
- `server.js`: 双模服务网关，同时负责 WebSocket 流量代理（`127.0.0.1:10000`）与 Clash 动态订阅渲染（`/clash`）。
- `/home/niu/clash/cloady-airport.zip`: 准备好的打包压缩包，可直接在 Cloady 网页上传。

---

## 节点协议特性

- **协议**: VLESS + WebSocket (WS) + TLS (443)
- **默认 UUID**: `d342d11e-d424-4583-b36e-524ab1f0afa4`
- **默认 WS Path**: `/airport`
- **订阅路由**:
  - Web 面板: `https://<你的-cloady-域名>/`
  - Clash 订阅链接: `https://<你的-cloady-域名>/clash`
  - VLESS 链接: `https://<你的-cloady-域名>/vless`
