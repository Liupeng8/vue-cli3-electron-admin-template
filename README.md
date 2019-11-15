# vue-cli3-electron-admin-template

## Project setup
```
yarn install or npm install
```

### Compiles and hot-reloads for development
```
yarn electron:serve or npm run electron:serve
```

### Compiles and minifies for production
```
yarn electron:build or npm run electron:build
```

### Lints and fixes files
```
yarn lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).


### 常见问题

```
一、主进程配置
```
protocol.registerSchemesAsPrivileged([{ scheme: 'app', privileges: { standard: true, supportFetchAPI: true, secure: true, corsEnabled: true }}])

```
1、跨域访问配置
```
  设置corsEnabled: true; BrowserWindow中设置webSecurity: false

```
2、访问谷歌V8引擎API（例如：localStroage，cookie, session等）
```
  设置supportFetchAPI: true，授权渲染进程访问V8引擎API
```

```

```