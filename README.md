# wxPay-git
[微信公众平台 - 微信支付 - 开发配置 - 服务器相关配置说明]：<br/>
    <br/>
    1、项目发布到我个人的服务器，服务器访问URL为http://yangyu85.com，端口为80。 
    <br/>
    <br/>
    2、由于我的服务器域名没有经过ICP备案，所以，只能选择【支付测试】栏目下的配置来进行支付开发，同时将自己的微信号添加到【测试白名单】，不然会报没有权限。 
    <br/>
    <br/>
    3、测试授权目录  ：  http://yangyu85.com/ ，由于支付页面chooseWXPay.jsp和WeixinJSBridge.jsp都是在项目的根目录下，所以，测试授权目录就配置为http://yangyu85.com/，而不是http://yangyu85.com/chooseWXPay.jsp/ 或者 http://yangyu85.com/WeixinJSBridge.jsp/ 
    <br/>
    <br/>
    4、对于像springmvc或者struts 相关的action请求进入支付页面，测试授权目录应该如何写呢？简单举个例子，如下： <br/>
        假如支付页面 chooseWXPay.jsp 是在/WEB-INF/views/目录下，而进入此页面的action请求路径为 http://yangyu85.com/wxpay/chooseWXPay ，那么，测试授权目录将配置为 http://yangyu85.com/wxpay/，而不是 http://yangyu85.com/wxpay/chooseWXPay/ 
    <br/>
    <br/>

[项目运行之前的一些必要条件配置]：

1、请在settings.properties中配置你的appid、mchid商户号、apikey支付密钥。<br/>
            appid: 微信公众平台 - 开发者中心 - 配置项 - 开发者ID - AppID(应用ID)<br/>
            mchid商户号：微信公众平台 - 微信支付 - 商户信息 - 基本数据 - 商户号<br/>
            apikey支付密钥：微信商户平台 - API安全 - 密钥设置<br/><br/>
2、请在wxinf.properties中配置你的appid、secret。<br/>
            appid： (同上)<br/>
            secret: 微信公众平台 - 开发者中心 - 配置项 - 开发者ID - AppSecret(应用密钥)<br/><br/>
            
[注意]：
com.zb.controller包下面的2个java类，代码中的静态全局变量openId的值，目前我是写成我自己的openid，由于只是测试微信支付的demo，所以对于openid的获取，我就不多做笔画。到时候你们自己实现获取openid，这里不影响实际支付测试。

<br/>
[补充]：
有的朋友由于不熟悉maven，对于jar的获取比较头疼，所以在这里，我将所有用到的jar进行了打包放在了项目的根目录jar目录下，请自行放置到项目中即可。
<br/>
项目中补充了5个功能，分别是：
关闭订单、查询订单、查询退款、下载对账单、申请退款。初学者可以借鉴一下代码，实现这3个功能的操作。其实代码都差不多的。很简单。
