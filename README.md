# Netlify Proxy Web

## 功能
- 使用 Netlify 免费部署网页代理
- 支持通配符子域名转发：
  `https://:subdomain.example.com/*` → `https://:subdomain.fast.example.com/*`
- 启用 Netlify 缓存（浏览器 1 小时，边缘节点 1 天）

## 部署步骤
1. Fork 本仓库到 GitHub
2. 登录 [Netlify](https://app.netlify.com/)，新建站点并绑定仓库
3. 部署完成后，在 Domain settings 添加 `*.example.com`
4. 在 DNS 添加：
   ```
   *.example.com   CNAME   你的项目名.netlify.app
   ```

## 使用示例
- 请求： `https://foo.example.com/page1`
- 实际转发： `https://foo.fast.example.com/page1`
- 返回结果自动缓存到 Netlify 边缘节点
