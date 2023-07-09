## Typora + Picgo + gitee 图床搭建

#### 搭建前配置

> 安装 PicGo 需要使用到 node.js，需在下载前安装。

**详情请参考：Node.js 安装及配置**

**搭建背景**

> 由于图片是在本地电脑上存储的，使用 Typore 做笔记插入的图片只能在自己电脑上查看，一旦离开了本地环境图片将会失效，故此需要将本地图片放到网络中去，这样无论什么在什么样的环境中都可以随时随地查看笔记喽。
>
> 使用 Typora + Picgo + gitee 可以很轻易实现这个目标
>
> 当然，如果你的图片访问量较大，更推荐你使用 Typora + Picgo + 腾讯云COS 组合
>
> 当图床访问使用流量过多时，可能会让 gitee 仓库变为私有，从而无法访问。
>
> ==以下两种方式都会给出，可自行选择==

#### 1、Picgo 下载

官网：[Release 2.3.0 · Molunerfinn/PicGo · GitHub](https://link.zhihu.com/?target=https%3A//github.com/Molunerfinn/PicGo/releases/tag/v2.3.0)

> 拉到最底部，找到与自己系统对应的安装包

![屏幕截图 2023-03-21 195917](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303221312371.png)

**更多版本：**[Tags · Molunerfinn/PicGo · GitHub](https://link.zhihu.com/?target=https%3A//github.com/Molunerfinn/PicGo/tags)

> 有更多版本可任意选择

#### 2、安装

![image-20230321200519491](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303221312879.png)

> 双击运行此文件，选择安装位置，其他默认即可

**安装成功运行后会出现此界面**

![image-20230321200743752](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303221312132.png)

> 注意：安装成功双击运行后，Picgo 会做最小化处理，在电脑上以托盘形式出现，注意查找（电脑右下角那一块的位置）

#### 3、Gitee

> 使用 gitee 来进行图片托管

**3.1、新建仓库**

![屏幕截图 2023-03-21 201356](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303221312907.png)

**3.2、输入仓库名称，设置模板选择 Readme 文件，点击创建** 

![屏幕截图 2023-03-21 201644](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303221312555.png)

> 创建完毕后选择管理

![](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303221312453.png)

> 在基本信息中选择开源，将此仓库变为开源仓库 ，点击保存

![屏幕截图 2023-03-21 202300](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303221312724.png)

> 接着依次选择  ==我的==——>==设置==——>==安全设置==——>==私有令牌==

![屏幕截图 2023-03-21 202803](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303221312240.png)

> 私有令牌描述可以任意，权限只需选择以下两项即可

![01](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303221312623.png)

> 提交后点击复制

![02](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303221313284.png)

> 注意：私有令牌需要保存好，如果忘记了或者没有保存，只需重新申请私有令牌即可

#### 3、腾讯云COS

**3.1 注册腾讯云COS账号**

网址：https://cloud.tencent.com/

![屏幕截图 2023-03-23 215552](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303232158413.png)



> **3.2 点击免费注册，然后一步步填写信息**

> **登陆完成后，选择控制台**

![屏幕截图 2023-03-23 215958](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303232201611.png)

> **3.3 搜索或选择对象存储**

![屏幕截图 2023-03-23 220215](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303232204390.png)

> **点击创建存储桶**

![屏幕截图 2023-03-23 220440](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303232206459.png)

> **填写信息，然后一直点下一步，确认配置**

![屏幕截图 2023-03-23 220746](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303232211603.png)

> **在存储桶列表可查看刚创建的存储桶**

![屏幕截图 2023-03-23 221346](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303232215995.png)

> **点击存储桶，==创建用于存储图片的文件夹==或者上传以前自己电脑上存储图片的文件夹**

![屏幕截图 2023-03-23 222430](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303232226412.png)



> **3.4 选择密钥管理，点击访问密钥**

![屏幕截图 2023-03-23 221548](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303232217801.png)

> **点击新建密钥（后面会用到）**

![屏幕截图 2023-03-23 221825](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303232221112.png)

#### 4、配置PicGo

> ==后面有腾讯云COS的图床设置，无需插件，可直接配置==

**4.1、点击插件设置，输入 gitee，选择如图所示的插件**

![屏幕截图 2023-03-21 204059](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303221313508.png)

**4.2、npm安装PicGo插件Gitee（需提前安装 Node.js）**

**测试 npm 是否可用**

**输入 npm -v 查看版本号，若可以成功显示，代表可用**

```
npm -v
```

![屏幕截图 2023-03-21 204601](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303221313608.png)

****

**使用命令进入到 PicGo 目录下**

![屏幕截图 2023-03-21 204739](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303221313590.png)

**在该目录下，使用 npm 命令安装gitee图床**

```
npm install picgo-plugin-gitee-uploader
```

**重启picgo**

**4.3、配置 Gitee **

**在图床设置中选择 ==gitee==** 只需对前面四项进行填写，后面两项不用写，==具体填写要求请参考下面==

> repo：用户名/仓库名 === 注意：==此处填写 https://gitee.com/（orange-oran/images）要以==gitee仓库路径中==的信息为准，最好直接复制；
>
> branch：填写分支  一般都是 ==master==;
>
> token：之前的私有令牌;
>
> path：如果在之前新建仓库中新建子文件夹，填写子文件夹名称在此处，将会把图片保存在那个文件夹中  一般image即可

**填写完成后点击确定**

![屏幕截图 2023-03-21 205129](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303221313152.png)

---

> **配置腾讯云COS  我的PicGo是2.3.1版本的，可能和2.3.0略有差异**

![屏幕截图 2023-03-23 223317](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303232246359.png)

> ==设定SecretId  设定SecretKey  设定AppId==

![屏幕截图 2023-03-23 223711](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303232239714.png)

> ==设定Bucket==（存储桶的名称）  ==设定存储桶区域==

![屏幕截图 2023-03-23 224214](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303232243378.png)

> ==点击设为默认图床==

#### 5、Typora 连接 Picgo

**5.1、依次点击 文件——>偏好设置——>选择图像，按照如图所示操作**

![屏幕截图 2023-03-21 210921](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303221313379.png)

**5.2、选好后，==点击 验证图片上传选项==**

> 如图所示，代表配置成功

![屏幕截图 2023-03-21 211446](https://imagesimages-1317416276.cos.ap-nanjing.myqcloud.com/image/202303221313708.png)

> 到此 Typora + Picgo + gitee 图床搭建成功，当你在 Typora 插入本地图片后，就会自动上传至 gitee 图床上

> 若使用 Typora + Picgo + 腾讯云COS，当你在 Typora 插入本地图片后，就会自动上传至 image文件夹中