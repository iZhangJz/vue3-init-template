# 前端万用 Vue3 模版

## 前端工程化

***需要在编辑器中打开配置***
- ```ESLint```    自动校验      
- ```Prettier```  代码美化格式化插件 
- ```Arco Design```   组件库 
- ```VueX``` 全局状态管理

## 功能
- **项目通用布局** header-content-footer 
- 导航栏**动态路由**配置 
- 使用 ```VueX``` 进行**全局状态管理**,管理已经登录的用户信息 
- **全局权限管理**,对用户进行角色权限校验 
- 预留了全局项目入口 ```App.vue``` 
- [基于 swagger 接口文档使用 openAPI 自动生成所有接口代码](https://github.com/ferdikoomen/openapi-typescript-codegen)
- 接入了**富文本编辑器** ```Markdown``` 编辑器, **支持表格, HighLight 高亮**. [富文本编辑器参考资料](https://github.com/bytedance/bytemd)

## 可能的问题
- 拉取代码出现错误 ```error Delete cr prettier/prettier``` 尝试使用 ```git config --global core.autocrlf false``` 解决


## 你需要做的事
- 将 ```package-lock.json``` 文件中的 ```name``` 属性 更改为你自己的项目名 
- 将 ```package.json``` 文件中的 ```name``` 属性 更改为你自己的项目名 
- 注意 ```TODO``` 标签，根据 ```TODO``` 提示完成你的开发