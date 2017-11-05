# MyHexo
http://regis25489.github.io
博客站Hexo资源文件

### Hexo使用
初始化目录
> hexo init

启动本地服务，浏览器输入http://localhost:4000，进行文章预览调试
> hexo server

每次部署的步骤，可按以下三步来进行。
>   hexo clean

>   hexo generate

>   hexo deploy

### 关键目录
#### 组成博客的原稿目录
> source/_posts

#### 设置发布地址
> _config.yml
```
deploy:
     type: git
     repo: https://github.com/Regis25489/Regis25489.github.io.git
     branch: master
```
然后，执行配置命令：
> hexo deploy

#### 一些常用命令：

> hexo new "postName" #新建文章

> hexo new page "pageName" #新建页面

> hexo generate #生成静态页面至public目录

> hexo server #开启预览访问端口（默认端口4000，'ctrl + c'关闭server）

> hexo deploy #将.deploy目录部署到GitHub

> hexo help #查看帮助

> hexo version #查看Hexo的版本

#### Mac安装Hexo出现报错
> { [Error: Cannot find module './build/Release/DTraceProviderBindings'] code: 'MODULE_NOT_FOUND' }
```
$ npm uninstall hexo-cli -g
$ npm install hexo-cli -g
```