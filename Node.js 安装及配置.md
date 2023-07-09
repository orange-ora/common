## Node.js 安装及配置

**背景：**

> Node.js对一些特殊用例进行优化，提供替代的[API](https://link.zhihu.com/?target=https%3A//baike.baidu.com/item/API/10154%3FfromModule%3Dlemma_inlink)，使得V8在非浏览器环境下运行得更好，V8引擎执行Javascript的速度非常快，性能非常好，基于Chrome JavaScript运行时建立的平台， 用于方便地搭建响应速度快、易于扩展的[网络应用](https://link.zhihu.com/?target=https%3A//baike.baidu.com/item/%E7%BD%91%E7%BB%9C%E5%BA%94%E7%94%A8/2196523%3FfromModule%3Dlemma_inlink)。

#### 一、安装 Node.js

**1、下载**

官网：https://nodejs.org/en

中文网：https://nodejs.cn/download/

> 建议使用中文网进行安装，方便较快。

![屏幕截图 2023-03-21 182628](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303221313631.png)

**2、安装解压到本地盘符中**

![屏幕截图 2023-03-21 185456](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303221313520.png)

**3、添加环境变量**

**3.1 进入环境变量，编辑【系统变量】下的变量【Path】**

![屏幕截图 2023-03-21 185916](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303221313717.png)

**3.2添加 Node.js 的安装路径**

![屏幕截图 2023-03-21 190124](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303221313102.png)



#### 二、验证是否安装成功

> 进入cmd命令窗口    ==node -v==  查看 Node.js 版本

```text
node -v
```

![屏幕截图 2023-03-21 190612](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303221313087.png)

> 输入 ==npm -v== 查看 npm 的版本

```text
npm -v
```

![屏幕截图 2023-03-21 191040](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303221314962.png)

> 如果两个命令都可以正常显示，则代表安装成功

---



#### 三、修改模块下载位置

> ==此步骤修改以后npm全局下载模块的保存位置，如果使用程度不高，以下配置可忽略。==

**1、查看npm默认存放位置**

> 使用 npm get prefix 命令查看npm全局模块的存放路径

```text
npm get prefix
```

> 使用npm get cache 命令查看npm缓存默认存放路径

```text
npm get cache
```

**2、在Node.js 安装目录下，创建“`node_global`”和 “node_cache”两个文件夹**

![屏幕截图 2023-03-21 191721](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303221314645.png)

**3、修改默认文件夹**

> 设置全局模块的安装路径到 “node_global” 文件夹  ==注意路径==

```text
npm config set prefix "D:\tools\Node.js\node_global"
```

> 设置缓存到 “node_cache” 文件夹  ==注意路径==

```
npm config set cache "D:\tools\Node.js\node_cache"
```

> 由于 node 全局模块大多数都是可以通过命令行访问的，还要把【node_global】的路径“`D:\tools\Node.js\node_global`”加入到【系统变量 】下的【PATH】 变量中，方便直接使用命令行运行

![屏幕截图 2023-03-21 192357](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303221314512.png)

**4、 测试默认位置是否更改成功**

> 经过上面的步骤，nodejs下载的模块就会自动下载到我们自定义的目录中，接下来我们测试一下是否更改成功。输入下面的命令：

```
npm install express -g
```

> 此时，nodejs 会自动地在node_global文件夹下创建【node_modules】子文件夹

![屏幕截图 2023-03-21 192757](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303221314558.png)

> 查看 node_modules文件夹下 express 模块是否已经被成功下载

![屏幕截图 2023-03-21 192921](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303221314577.png)

#### 四、设置淘宝镜像

**1、将npm默认的registry修改为淘宝registry**

> npm 默认的 registry ,也就是下载 npm 包时会从国外的服务器下载，国内下载会很慢，一般更换为淘宝镜像：[https://registry.npm.taobao.org](https://link.zhihu.com/?target=https%3A//registry.npm.taobao.org)

**1.1、查看当前使用的镜像路径**

```
npm config get registry
```

> **默认地址为：**[https://registrynpmjs.org/](https://link.zhihu.com/?target=https%3A//registrynpmjs.org/)

**1.2、更换 npm 为淘宝镜像**

```
npm config set registry https://registry.npm.taobao.org/
```

**1.3、 检查镜像是否配置成功 再次执行npm config get registry，检查当前的镜像路径**

```
npm config get registry
```

![屏幕截图 2023-03-21 193522](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303221314103.png)



**2、全局安装基于淘宝源的 cnpm **

> 由于npm的服务器在海外，所以访问速度比较慢，访问不稳定 ，==cnpm==的服务器是由淘宝团队提供，服务器在国内，==cnpm是npm镜像==，一般会同步更新，相差在10分钟，所以cnpm在安装一些软件时候会比较有优势。但是==cnpm一般只用于模块安装，在项目创建与卸载等相关操作时仍使用npm==2.1、全局安装基于淘宝源的cnpm

**2.1、全局安装基于淘宝源的cnpm**

```
npm install -g cnpm
```

**2.2、本地查看cnpm模块**

![屏幕截图 2023-03-21 194207](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303221314030.png)

**2.3、执行命令查看cnpm是否安装成功**

```
cnpm -v   
```

![屏幕截图 2023-03-21 194403](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303221314919.png)

> 输入命令若是如图所示结果，则代表 ==cnpm== 配置成功。

> 欢迎使用 Node.js 