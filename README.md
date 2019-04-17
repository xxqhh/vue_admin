# web端vue+server端express项目开发

# web端vue项目

## 一、运行环境
node

## 二、开发环境搭建
```
# 将项目拉到本地
git clone 项目地址

# cd到本地项目下
cd ../vueProject

# 安装项目运行需要的依赖包
npm install / cnpm install  (注：如需运行cnpm install，需先安运行npm install cnpm安装cnpm)

# 在本地开发时，运行项目
npm run dev / cnpm run dev

```
开发环境，在执行完上述步骤后，浏览器访问http://localhost:8082，可跳转到对应页面 （推进chrome浏览器）

## 三、项目发布
在开发环境中完成项目开发后，要将项目发布到服务器（如nginx服务器），首先在./config/prod.env.js的BASE_URL单引号内填上
请求地址（Server的接口地址，该处必须在双引号中将url地址用单引号包住，因为需要直接返回字符串路径时，就必须采用单引号把
字符串内容括起来，如BASE_URL:"'http://192.168.1.111:4000/api'"），在url后加端口号加'/api'，这是由于F2FAdminServer
端接口统一用了'url' + ':' + '端口号' + '/api'的形式，在完成上述修改后，进行下面的操作。

```
# 项目打包
npm run build / cnpm run build

# 查看是否生成了dist文件夹
在文件夹下包括index.html文件和static文件，如作了标题旁的图片，可能还有logo.ico

# cd到dist文件夹下
cd ./dist/

# 将dist文件夹下的static的文件夹与index.html文件直接放在nginx服务器根目录下

# 配置nginx，在nginx.conf文件中修改所要监听的端口

# chrome浏览器访问对应的域名，如http://xxx.xxx.com:123/
如部署到个人服务器，没有域名，访问地址为http:// + ip + ：端口号

```
在跳转到登录页面后，输入数据库对应表（如admin）中对应的账号/密码（如：lilei/123456）,若跳转到首页页面，则部署成功，否则根据所出现
的问题（按F12调出控制台进行查看），解决出现的问题，然后重复上述步骤。

# server端express项目

## 一、概述
server端服务器部署分为node.js服务器和MySQL数据库两部分工作

## 二、node.js服务器相关


