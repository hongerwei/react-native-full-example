# 小明找厕所
## 1、express开发
### 1.1 npm环境设置
1. 安装node软件：<https://nodejs.org/en>
2. 安装淘宝滤镜：npm install -g cnpm --registry = https://registry.npm.taobao.org
3. 设置全局的npm从国内下载资源， npmrc添加配置。mac下面地址为 /Users/liumingming/.npmrc，修改strict-ssl=true 和 registry=https://registry.npm.taobao.org

### 1.2 express环境搭建
1. 安装express-generator：npm install -g express-generator，用户快速创建express项目
2. 生成项目模块：进入到项目目录 /User/liumm/A_study/app/toiletApp 下面，执行命令 express -e service，其中-e为ejs模块简写
3. 在服务端项目安装依赖：进入服务端项目 /User/liumm/A_study/app/toiletApp/service 执行命令 cnpm install，安装依赖类库
4. 启动项目：使用在当前目录中使用 npm start启动项目，其中start命令在package.json已经配置
5. 预览：启动已经开发本地的 localhost:3000，访问地址即可看见启动的页面
6. 修改预览：项目中app.js 文件为服务启动入口路径。修改项目下面 views/index.ejs文件，重启服务进行查看
7. express修改热加载：安装supervisor，npm install supervisor -g，修改项目自动更新

### 1.3 项目文件目录组织
```
    service
            bin
                www                       //为项目启动路径
            node_modules                  //项目所依赖lib，初创项目使用npm install得到
            public                        //静态文件路径，其后css或者js文件不加public，app.js文件已经设置
                css                       //项目中所有的ejs模板的css文件
                data                      //项目未使用数据库，使用json进行数据交互
                    config.json           //阅读模块首页配置json
                    cookies.json          //开心一刻数据json
                    it.json               //IT质询json
                    manager.json          //管理json
                    prose.json            //散文json
                js                        //页面前端交互js文件夹
                    lib                   //第三方lib包，包括常用的jquery、bootstrap
                    login.js              //首页登录js文件
                    ...                   //等等
            routes                        //后端路由
                 data.js                  //数据交互后端路由
                 index.js                 //首页
            views                         //前端页面视图ejs
                error
                    404.ejs
                login.ejs
                index.ejs
                tuijian.ejs
                edit.ejs
            app.js                        //前端主入口文件
            package.json                  //配置信息，依赖配置部分相当于java的pom.xml文件
```
## 2、app开发
### 2.1、jsbundle文件优化加载
打包jsbundle文件 加载成功便于app加载
react-native bundle --entey-file index.ios.js --platform ios --dev false --bndle-output main.ios.jsbundle
