# 使用 Microsoft 标识平台创建受保护的 Web API
Microsoft 标识平台可帮助开发者构建应用程序，允许用户使用多种账户登录到这些应用程序，并授权访问你自己的 API 或 Microsoft 提供的 API（例如 Microsoft Graph）。  

Microsoft 标识平台提供符合 OAuth 2.0 和 OpenID Connect 标准的身份验证服务，用于开发者实现对多种账户类型进行身份验证，包括在 Azure AD 中配置的企业用户、用户个人的 Microsoft 账户和各种社交账户。

![](/assets/img/convergence-scenarios-webapi.svg "")

本篇包含以下内容：
- 开发本地 SPA 应用
- 在 Microsoft 标识平台中注册 SPA 应用
- 登录、注销和保护路由

本篇介绍在Angular应用中集成Azure AD(Azure Active Direcotry)身份验证服务，

利用Azure AD实现使用微软账号登录到应用并获取用于调用受Active Direcotry保护的API的令牌。

### 准备一个angualr应用

使用npm安装Angular CLI:

```
npm install -g @angular/cli
```

使用Angular CLI创建一个脚手架工程:

```
ng new msal-angular-tutorial
```

安装Microsoft身份验证库MSAL:

```
npm install @azure/msal-browser @azure/msal-angular
```

创建home和profile两个页面的组件：
```
ng generate component home
ng generate component profile
```

访问profile页面时，需要调用受保护的API获取在页面中展示的数据，因此访问该页面时必须要登录。
