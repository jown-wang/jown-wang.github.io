# 使用 Microsoft 标识平台创建受保护的 Web API

Microsoft 标识平台可帮助开发者构建应用程序，允许用户使用多种账户登录到这些应用程序，并授权访问你自己的 API 或 Microsoft 提供的 API（例如 Microsoft Graph）。

Microsoft 标识平台提供符合 OAuth 2.0 和 OpenID Connect 标准的身份验证服务，用于开发者实现对多种账户类型进行身份验证，包括在 Azure AD 中配置的企业账号、个人 Microsoft 账号和社交账号。

使用 OAuth2 访问令牌来保护 Web API 的流程如下所示：

1. 客户端从 /token 节点获取 Oauth bearer 令牌；
2. 客户端在 Authorization 头中设定访问令牌，然后调用 API；
3. API 从 /discovery 节点获取令牌校验元数据；
4. 验证令牌，返回受保护的资源。

![图片](/assets/img/convergence-scenarios-webapi.svg)

本篇介绍使用 Microsoft 标识平台保护 Spring Boot Web API, 包含以下内容：

- 使用 Spring Boot 开发 Web API
- 在 Microsoft 标识平台中注册该 Web API
- 访问受保护的资源

## 使用 Spring Boot 开发 Web API