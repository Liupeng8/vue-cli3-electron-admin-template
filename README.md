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
  privileges中设置corsEnabled: true; BrowserWindow中设置webSecurity: false

```
2、访问谷歌V8引擎API（例如：localStroage，cookie, session等）
```
  设置supportFetchAPI: true, standard: true，授权渲染进程访问V8引擎API

```
3、使用vue-devtools
  先安装vue-devtools,命令：npm install vue-devtools -D
  因vue-cli-plugin-electron-builder使用了webpack，导致vue-devtools在加载vender/manifest.json时路径错误而无法启动，需手动修改一下路径，暂时未找到方法。
  const extPath = path.join(__dirname, '..', 'vender')  修改成  const extPath = path.join(__dirname, '../node_modules/vue-devtools', 'vender')