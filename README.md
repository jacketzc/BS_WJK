## my temperament管弦乐器销售
- 是一个基于[Spring Boot](https://spring.io/projects/spring-boot/)和[Vue.js](https://cn.vuejs.org)的web商城系统
- 包含了商城的后台管理系统,手机h5


## 技术选型
- 核心框架：Spring Boot
- 数据库层：Spring data jpa
- 数据库连接池：Druid
- 缓存：Ehcache
- 前端：后台管理基于[element](http://element-cn.eleme.io)，手机端界面基于[vant](https://youzan.github.io/vant/#/zh-CN/intro)


## 快速开始
- 克隆本项目
- 导入idea或者eclipse
- 确保开发工具下载并安装了lombok插件，另外由于lombok有版本差异，如果出现问题，可以更新maven以来中lombok的版本来解决
- 创建数据库：linjiashop
     ```sql
    CREATE DATABASE IF NOT EXISTS linjiashop DEFAULT CHARSET utf8 COLLATE utf8_general_ci; 
    CREATE USER 'linjiashop'@'%' IDENTIFIED BY 'linjiashop191028';
    GRANT ALL privileges ON linjiashop.* TO 'linjiashop'@'%';
    flush privileges;
    ```     
- 下载项目测试数据的图片：链接： ，将图片存放到t_sys_cfg表中system.file.upload.path配置的目录下(注意该目录未绝对路径，该目录可以通过“系统管理”-“参数管理”进行配置)
- 启动后台管理
    - 启动后台管理api服务:linjiashop-admin-api
        - 修改linjiashop-admin-api中数据库连接配置  
        //本项目使用了腾讯云数据库，如果不需要使用本地数据库则使用默认配置即可                
        - 启动linjiashop-admin-api主类：cn.enilu.flash.api.AdminApiApplication，访问http://localhost:8082/swagger-ui.html ， 保证api服务启动成功
    - 启动后台管理的前端界面:linjiashop-admin
        - 运行 npm install --registry=https://registry.npm.taobao.org
        - 运行npm run dev
        - 启动成功后访问 http://localhost:9528 ,登录，用户名密码:admin/admin 
- 启动手机端商城
    - 启动手商城的api服务:linjiashop-mobile-api   
        - 修改linjiashop-mobile-api中数据库连接配置
        - 启动linjiashop-mobile-api主类：cn.enilu.flash.MobileApiApplication,访问http://localhost:8081/swagger-ui.html ， 保证api服务启动成功
    - 启动手机商城的前端:linjiashop-mobile
        - 运行 npm install --registry=https://registry.npm.taobao.org
        - 运行npm run dev
        - 启动成功后访问 http://localhost:8080/#/index
