[TOC]
---
## 一、项目相关
### 1. 资源
+ 代码路径：https://code.aliyun.com/
+ 文档路径：https://code.aliyun.com/
+ iconfonts：http://www.iconfont.cn/
    + 登陆邮箱：`core2962@dingtalk.com`
    + 登陆名：`tamaidan`
+ 对接人员：
    + 后台：
    + UI：
    + 前端：
### 2. 安装调试
+ 依赖环境：
    + [node >= 4.0.0](https://nodejs.org/en/)
    + npm >= 3.0.0
    + cnpm `npm install -g cnpm --registry=https://registry.npm.taobao.org`
+ 代码更新：`git clone git@code.aliyun.com:435361870/tamaidan.git`  
+ 依赖安装：`cnpm install`  
+ 项目运行：`npm run dev`
+ 项目打包：`npm run build`, 访问：http://localhost:8080/home
    > **注意**：项目打包/启服时注意切换环境变量(`src/src/env_checkout.js`)
    > 0 --> 本地服
    > 1 --> 线上测试服
    > 2 --> 线上正式服

## 二、代码相关
### 1. 代码结构
```
│  .babelrc
│  .editorconfig         ---> 代码风格
│  .gitignore            ---> 忽略配置
│  .postcssrc.js
│  index.html
│  package-lock.json
│  package.json          ---> 依赖文件
│  README.md
│  share.html
│  
├─build                  ---> webpack打包配置文件
│      
├─config                 ---> webpack公共配置
│         
├─src                    ---> 项目工作区
│  │  App.vue           
│  │  env_checkout.js    ---> 环境变量
│  │  main.js
│  │  
│  ├─base                ---> 基础组件
│  │          
│  ├─common              ---> 公共方法、样式、字体文件
│  │          
│  ├─components          ---> 子组件
│  │          
│  ├─css
│  │      
│  ├─filter
│  │      
│  ├─pages
│  │          
│  ├─router              ---> 路由
│  │      
│  ├─store               ---> store仓库
│  │      
│  └─utils
│          
└─static
```

## 三、技术栈及快速入门
### 1. 环境
+ [node](https://nodejs.org/en/)
+ [cnpm](https://npm.taobao.org/) `npm install -g cnpm --registry=https://registry.npm.taobao.org`
### 2. 构建工具
+ [webpack](https://doc.webpack-china.org/concepts/)
### 3. 代码管理工具
+ [git](https://git-scm.com/book/zh/v2)
### 4.开发语言
+ [vue](https://cn.vuejs.org/)
+ [vue-rouer](https://router.vuejs.org/zh-cn/)
+ [vuex](https://vuex.vuejs.org/zh-cn/)
+ [ES6](http://es6.ruanyifeng.com/)

## 四、开发相关
### 1. webpack配置 环境切换 
+ 环境变量切换文件位置：`src/env_checkout.js`
+ `webpack`基本配置文件位置：`src/config/index.js`      

> 通过修改`src/config/index.js`中build对象下的`assetsSubDirectory`
`assetsPublicPath`来实现不同环境下的打包切换
//路径拼接规则  assetsSubDirectory/assetsPublicPath  

### 2. 页面应用
#### 基础组件
 + `slider`         轮播组件，依赖 [betterscroll](https://ustbhuangyi.github.io/better-scroll/doc/zh-hans/)
 + `confirm`        确认操作弹框
 + `datePicker`     时间选择器,依赖 [mint-ui](http://mint-ui.github.io/#!/zh-cn)
 + `loading`        loading加载
 + `numberPicker`   数字选择器,依赖 [mint-ui](http://mint-ui.github.io/#!/zh-cn)
 + `rangePIcker`    范围选择,依赖 [mint-ui](http://mint-ui.github.io/#!/zh-cn)
 + `scroll`         滚动组件，依赖 [betterscroll](https://ustbhuangyi.github.io/better-scroll/doc/zh-hans/)
#### 公共区域
 + js
    <details>

    + `date.js`             时间操作相关
    + `cache.js`            缓存操作相关
    + `checkout_url.js`     ulr路径
        ```
        注意：根据不同的环境切换了域名
        baseHttp = 'http://192.168.10.49:8080/'  //线下本地
        baseHttp = 'https://m.tamaidan.com/backtest/'  //线上测试
        baseHttp = 'https://m.tamaidan.com/back/'  //线上正式
        ```
    + `checkoutPhone.js`    校验手机号码
    + `common.js`           支付配置与调用微信支付返回new Promise()
    + `handle_dom.js`       DOM操作相关
    + `handle_img.js`       图片地址拼接
        ```
        服务端饭回来的图片地址都是地址片段，需要前端拼接成完整的url地址
        ```
    + `numberHandler.js`    数字相关
    + `phoneType.js`        设备系统校验
    + `pickerSlots.js`      picker数据slots
    + `share.js`            微信分享配置
        ```
        推荐人手机号是通过点击他人分享的链接后得到的
        ```
    + `SharingPerson.js`    推荐人手机号处理
    </details>

 + css
     <details>

    + 1
    + 2
    + 3
    + 4
 </details>

 + [fonts](http://www.iconfont.cn/)
    + 登陆邮箱：`core2962@dingtalk.com`
    + 登陆名：`tamaidan`
#### 子组件
 + components
    <details>

    + `coreAddress`             用户的地址的子组件，根据地址的列表，循环地址的列表。
                                方法：根据地址的id删除地址、根据地址的id编辑地址、根据地址的状态改变地址的默认地址状态
    + `experience`              体验页面的子组件，获取体验的文字与图片的列表。里面有交押金弹框的提醒与调用支付
    + `bloodSugarMap`           血糖图表
    + `controlledDrug`          个人中心中的控制药物选择
    + `coreGoodsSimpleDetail`   商品列表中商品简介
    + `coreOrderClassify`       订单详情页
    + `coreZtoInfo`             物流信息(中通)
    + `myfooter`                footer导航切换
    + `pageTitle`               各页面标题头
    + `TheLogisticsInform`      物流暂停提示
    </details>
#### 页面
 + page
    <details>

    + `auth`                鉴权页，进入此应用的第一个页面，获取微信授权和获取用户的微信信息 ，根据微信返回的code判定用户是否授权，获取code之后请求数据可以获取用户信息，获取用户信息之后进行本地存储
    + `bloodSugarDoctor`    血糖医生，展示/输入用户填写的血糖信息
    + `coreAddress`         地址列表,获取用户的地址列表
    + `coreGoodsList`       商品列表，展示所有商品
    + `coreGoodsDetail`     商品详情，展示商品的价格、产品图、物流等详细信息
    + `coreSearch`          商品搜索
    + `home`                商品广告页，展示网站当前推荐的产品
    + `coreOrderDetail`     订单页
    + `corePersonalCenter`  个人中心，显示用户的头像，手机号；
    + `coreRecommond`       我的奖励，奖励积分，根据下单与最后一次领取时间推断是否可以领取，周期180d    
    + `errorPath`           请求错误路径会跳转此页面
    + `experience`          体验页面，交押金，领取血糖仪，根据用户的状态判定是交押金还是领取血糖仪 子组件为：`components/experience`
    + `freePager`           领用、优惠购买试纸，正常购买试纸。根据领用血糖仪的时间（或者最新的一次领取试纸的时间）判定是否可以领取试纸，领取周期：180d
    + `help`                帮助页面，可以查询客服电话，反馈信息，查看服务条款
    + `oldHealth`           根据类型划分商品，请求同一类型商品的列表。
    + `coreCompletion`      订单完成页面，点击跳转到查看订单页面
    + `coreOrderConfirmTemp`订单确认页，根据商品的列表、地址的id、加密串进行去下单调用支付。里面有地址的选择、添加与修改
    + `regist`              用户注册，根据用户的手机号获取短信信息。根据信息进行注册，返回用户的信息。
    + `share`               分享页面，一个分享的指引弹框
    + `shoppingCart`        用户的清单，根据用户获取加入清单的商品列表。计算选择商品列表的费用计算；方法： 购物车商品的添加 购物车左划删除 购物车选择商品 
    + `waitingPay`          待支付，支付失败之后等待支付页面，根据订单的orderId重新进行支付或者取消订单
 </details>

#### 路由
+ router
    + index.js
    + map.js
   
 
#### 数据管理
+ store [vuex](https://vuex.vuejs.org/zh-cn/actions.html)数据管理，通过vuex数据核心概念将文件分类，方便管理
   + getters.js    获取数据
   + actions.js
   + mutations.js  更改数据状态
   + mutation-types.js
   + state.js
   + index.js  `new store`
 
#### 依赖管理
+ package.json

## 五、开发问题
### 1. 微信JS-SDK(此总结仅使用与SPA/History模式下)

使用微信JS-SDK步骤：(这里简单说明一下，具体步骤详解看[微信JS-SDK说明文档](https://mp.weixin.qq.com/wiki?t=resource/res_main&id=mp1421141115))
1. 去微信公众平台设置’js接口安全域名‘
2. 引入js接口文件
    + 引入链接：`http://res.wx.qq.com/open/js/jweixin-1.2.0.js`
    + 加载模块：`npm install weixin-js-sdk`
3. 通过config接口注入权限验证配置
4. 通过ready接口处理成功验证(ready函数中执行调用的微信API)
5. 通过error接口处理失败验证

### 2. 错误总结：
调用微信内置的API(分享| 支付等)大部分都需要进行权限配置，配置出错基本可以分为两大类：
1. `wx.config()`配置中，在开启`debug:true`的情况下，如果提示配置失败基本都是页面url的锅，盯着url来解决问题就可以了，无论是前端还是服务端
2. 如果配置信息没有错误，只是要调用的API各种间歇性无法调用，应该是配置函数执行时机出现了问题，设置个延迟函数基本就解决了，但比较hack,应该有更好的办法，暂时还没想到

---
> **如果你遇到了config权限配置经常出错，需要先了解下面内容来帮助你解决问题**

这张图模拟了一个用户进入你的应用（网页）后的一些行为，包括：
1. 点击链接或按钮跳转到其他页面
2. 刷新页面
其中：
    + currentPage表示你正在看的页面
    + langdingPage表示落地页，也就是浏览器认为的页面

> Andriod系统对url的识别机制

![image](https://user-images.githubusercontent.com/24493052/36840116-da2d6530-1d7e-11e8-86e4-1f81a3388e68.png)

> Ios系统对url的识别机制

![image](https://user-images.githubusercontent.com/24493052/36839484-2e5a663c-1d7d-11e8-80cd-1e32b7d394a8.png)

如上，Andriod系统更符合我们对url的认知，而Ios系统中的每个页面的url都是刚进入项目的第一页的url,除非是刷新页面；即：在SPA模式下：
+ Ios中，页面A为整个项目的真实url
+ Andriod中，每次路由跳转都会产生新的url
> 微信js-sdk配置加密所校验的url是落地页url（即：`landingPage`）,所以以下情况若调用微信API需要在当前页面配置:
> + `Ios`进入项目的第一页
> + `Ios`页面刷新后
> + `Andriod`路由跳转或页面刷新后  
---
① 在SPA/history模式下，不同系统对url的识别机制存在差异（如下图）：

+ `Ios`（所有页面的url等于落地页url
进入项目的落地页为配置页，只需要在落地页配置一次即可
+ `Android`（每次页面跳转都会产生新的url
需要调用微信api的页面需单独配置

② Sha1加密注意事项

+ 向后端发送的`url`进行sha1加密，`url`必须是动态获取（放在函数中动态执行）
+ 本项目下向后端传入的url需进行`encodeURIComponent`转码，防止参数中的’&’出现混淆

③ 自定义分享配置注意事项：

+ 分享链接link: 必须和公众号中设置的js安全域名一致（本项目中必须是`m.tamaidan.com`）,并且不需要使用`encodeURIComponent`转码，否则安卓端异常
+ 若配置方法是在导航守卫中执行，注意`weixin API`的加载校验为异步，配置信息要在`weixin`校验完成后执行

### Ⅱ 鉴权与支付
+ 

---
### 微信的授权
> 授权场景
+ 根据网页的url判定code是否存在。
+ 如果code存在则授权成功，根据code请求接口获取用户的信息
+ 如果code不存在则获取用户的code，调用微信授权。在auth.vue中代码如：
``` javascipt
    function getCode(){
    var query = {
        domain: 'https://open.weixin.qq.com/connect/oauth2/authorize',//请求code的域名
        appid: 'wxa69d932fd28deb71',//微信的公众号的标识
        scope: 'snsapi_userinfo',//静默授权  //snsapi_userinfo(非静默)
        state: saveSharingPerson(),//分享手机号的获取
        redirect_uri: encodeURIComponent(window.location.href),//wx重定向地址 redirect_uri
        response_type: 'code'//返回类型，请填写code
    }
    var url = query.domain + '?appid=' + query.appid + '&redirect_uri=' + 'https://m.tamaidan.com'+_self.$basePath+'/auth' + '&response_type=code&scope=snsapi_base&state='+query.state+'#wechat_redirect'
    window.location.href = url//调用地址
}
```
+ 获取用户信息成功，授权成功
> 授权支付
+ expost payApi(data)
+ return new Promise()
+ wx.config()微信配置
    + `debug`          开启调试模式，调用所有api的返回值会在客户端alert打印出来 如果在pc打开会以log形式打印出来
    + `appId`          公众号的唯一标识
    + `timestamp`      必填,生成签名的时间戳
    + `nonceStr`       必填，生成签名的随机数
    + `signature`      必填，签名
    + `jsApiList`      需要使用的JS接口列表
+ wx.ready配置完成后
+ weixinJSBridege.invoke() 调用支付配置
    + appId     公众号名称，由商户传入
    + timeStamp 时间戳，自1970年以来的秒数
    + nonceStr  随机串
    + package   订单详情扩展字符串  统一下单接口返回的prepay_id参数值，提交格式如：prepay_id=***
    + signType  微信签名方式
    + paySign   微信签名
### Ⅲ axios的信息过滤与拦截
+ axios.interceptors.response.use((response)=>{})
    + axios的过滤方法 
    + response为服务器端返回的数据
    + 根据情景进行条件判定
### Ⅳ flex布局
### flex布局语法
#### 网页布局（layout）是 CSS 的一个重点应用。
![image](http://www.ruanyifeng.com/blogimg/asset/2015/bg2015071001.gif)\
* 布局的传统解决方案，基于盒状模型，依赖 display 属性 + position属性 + float属性。  
* 它对于那些特殊布局非常不方便，比如，垂直居中就不容易实现。
#### 支持浏览器
![image](http://www.ruanyifeng.com/blogimg/asset/2015/bg2015071003.jpg)
#### 基本概念
+ 采用 Flex 布局的元素，称为 Flex 容器（flex container），简称"容器"。  
它的所有子元素自动成为容器成员，称为 Flex 项目（flex item），简称"项目"。
容器默认存在两根轴：水平的主轴（main axis）和垂直的交叉轴（cross axis）。  
主轴的开始位置（与边框的交叉点）叫做main start，结束位置叫做main end；  
交叉轴的开始位置叫做cross start，结束位置叫做cross end。
项目默认沿主轴排列。  
单个项目占据的主轴空间叫做main size，占据的交叉轴空间叫做cross size.  
![image](http://www.ruanyifeng.com/blogimg/asset/2015/bg2015071004.png)
#### 容器的属性
以下6个属性设置在容器上。

+ flex-direction
  + row →(默认) ：主轴为水平方向，起点在左端
  + row-reverse ← ：主轴为水平方向，起点在右端
  + column ↑ ：主轴为垂直方向，起点在上沿
  + column-reverse ↓ ：主轴为垂直方向，起点在下沿
+ flex-wrap
  + nowrap(默认)：不换行
  + wrap：换行，第一行在上方
  + wrap-reverse ：换行，第一行在下方
+ flex-flow属性是flex-direction属性和flex-wrap属性的简写形式，默认值为 row nowrap
+ justify-content
  + flex-start（默认值）：左对齐
  + flex-end ：右对齐
  + center 居中
  + space-between ：两端对齐，项目之间的间隔都相等
  + space-around ：每个项目两侧的间隔相等。所以，项目之间的间隔比项目与边框的间隔大一倍
+ align-items
  + flex-start : 交叉轴的起点对齐。
  + flex-end：交叉轴的终点对齐。
  + center：交叉轴的中点对齐。
  + baseline: 项目的第一行文字的基线对齐。
  + stretch（默认值）：如果项目未设置高度或设为auto，将占满整个容器的高度。
 + align-content
  + flex-start：与交叉轴的起点对齐。
  + flex-end：与交叉轴的终点对齐。
  + center：与交叉轴的中点对齐。
  + space-between：与交叉轴两端对齐，轴线之间的间隔平均分布。
  + space-around：每根轴线两侧的间隔都相等。所以，轴线之间的间隔比轴线与边框的间隔大一倍。
  + stretch（默认值）：轴线占满整个交叉轴。
#### 项目的属性
> 以下6个属性设置在项目上。
  + order
    + 属性定义项目的排列顺序。数值越小，排列越靠前，默认为0。
  + flex-grow
    + flex-grow属性定义项目的放大比例，默认为0，即如果存在剩余空间，也不放大。
  + flex-shrink
    + flex-shrink属性定义了项目的缩小比例，默认为1，即如果空间不足，该项目将缩小。
  + flex-basis
    + flex-basis属性定义了在分配多余空间之前，项目占据的主轴空间（main size）
  + flex
    + flex属性是flex-grow, flex-shrink 和 flex-basis的简写，默认值为0 1 auto。后两个属性可选。
  + align-self
    +align-self属性允许单个项目有与其他项目不一样的对齐方式，可覆盖align-items属性。默认值为auto，表示继承父元素的align-items属性，如果没有父元素，则等同于stretch。
