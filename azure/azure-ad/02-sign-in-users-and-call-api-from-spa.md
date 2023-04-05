# 使用企业用户登录 SPA 应用并访问受保护的 API

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
