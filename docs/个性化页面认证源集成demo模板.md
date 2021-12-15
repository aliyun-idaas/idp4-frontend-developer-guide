## 一、短信认证源
#### 1、模板代码
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Title</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <link rel="stylesheet" href="@resourceServerDomain@/static/bootstrap/css/bootstrap.min.css">
  <link rel="stylesheet" type="text/css" href="@resourceServerDomain@/static/css/custom-page-style.css">
  <style>
        /*
            在这里写自定义样式

            */
           /*
            在这里写自定义样式

            */
          .window-w-h {
            width: 100%;
            height: 100%;
          }
          .window-w-h .login-page {
            height: 100%;
          }
          .content-body-login {
            height: 100%;
            display: flex;
            flex-direction: column;
          }
          .content-body-login header {
            height: 70px;
            width: 100%;
            border-bottom: 1px solid #F0F0F0;
          }
          .content-body-login header .header-content {
            height: 100%;
            width: 1100px;
            margin: 0 auto;
            display: flex;
            align-items: center;
          }
          .content-body-login header .header-content .logo-img {
            width: 172px ;
          }
          .content-body-login section {
            flex: 1;
          }
          .content-body-login section .section-content {
            width: 1100px;
            margin: 0 auto;
            display: flex;
            height: 100%;
            padding-bottom: 50px;
          }
          .content-body-login section .section-content .aside {
            width: 50%;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
          }
          .content-body-login section .section-content .aside-left {
            padding: 0 13px;
            display: flex;
            flex-direction: column;
          }
          .content-body-login section .section-content .aside-left .login-bg {
            width: 100%;
            height: 418px ;
            background: url(http://117.50.108.64:9911/frontend/login/img/login-bg.png) no-repeat center;
            background-size: cover ;
            position: relative;
          }
          .content-body-login section .section-content .aside-left .bg-tips {
            font-size: 18px;
            color: #fff;
            background-color: #766655;
            padding: 18px 15px ;
            letter-spacing: 2px;
            width: 100%;
          }
          .content-body-login section .section-content .aside-right .login-con {
            padding: 0;
            box-shadow: none;
            width: 350px;
          }
          .content-body-login section .section-content .aside-right .login-con .login-body {
            padding: 0;
            padding-top: 35px ;
          }
          .content-body-login section .section-content .aside-right .captcha-content {
            position: absolute;
            left: -51px;
            top: 8px;
          }
          .content-body-login section .section-content .aside-right .login-content-head {
            min-height: 64px;
            display: flex;
            position: relative;
            border-bottom: 1px solid #eee;
          }
          .content-body-login section .section-content .aside-right .login-content-head .item {
            width: 50%;
            text-align: center;
            display: inline-block;
            font-size: 16px;
            color: #666;
            padding: 20px 0;
            position: relative;
            cursor: pointer;
          }
          .content-body-login section .section-content .aside-right .login-content-head .item::before {
            content: "";
            position: absolute;
            width: 100%;
            height: 2px;
            bottom: 0;
            left: 0;
            background: #F39339;
            display: none;
          }
          .content-body-login section .section-content .aside-right .login-content-head .item:hover,
          .content-body-login section .section-content .aside-right .login-content-head .item.active {
            color: #F39339;
          }
          .content-body-login section .section-content .aside-right .login-content-head .item:hover::before,
          .content-body-login section .section-content .aside-right .login-content-head .item.active::before {
            display: block;
          }
          .content-body-login section .section-content .aside-right .forget_password {
            color: #F39339;
            cursor: pointer;
            font-size: 14px;
          }
          .content-body-login section .section-content .aside-right .forget_password:hover {
            color: #FA8117;
          }
          .content-body-login section .section-content .aside-right .qr-box {
            padding: 0;
          }
          .content-body-login section .section-content .aside-right .login-box {
            margin-bottom: 0;
            min-height: 330px;
            display: none;
          }
         .content-body-login section .section-content .aside-right .login-box.active{
          display: block;
         }
          .permit-information {
            width: 100%;      
            text-align: center;
            height: 50px;
            border-top: 1px solid #F0F0F0;
          }
          .permit-information .footer-content {
            height: 100%;
            width: 1100px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
          }
          .permit-information .footer-content span {
            font-size: 12px;
            color: #B7B7B7 ;
          }
          .input-group-addon{
            font-size: 12px;
            color: #338DD6;
            cursor: pointer;
            display: inline-block;
          }
          .login-page .login-body .code-group .input-group-addon{
            width: 108px;
          }
          .form-control:-webkit-autofill{
            box-shadow: 0 0 0px 1000px white inset !important;
          }
          @media (max-width: 1020px) {
            .permit-information .footer-content {
              width: auto;
              padding: 0 15px;
            }
          }

          @media (max-width: 1020px) {
          .login-page .content-body-login .header-content,
            .login-page .content-body-login .section-content {
              width: auto;
          }
          .login-page .content-body-login .header-content {
              justify-content: center;
          }
          .login-page .content-body-login .section-content .aside-left {
              width: 0;
              display: none;
          }
          .login-page .content-body-login .section-content .aside-right {
              width: 100%;
              padding-top: 50px;
          }
          .login-page .content-body-login .section-content .aside {
              justify-content: flex-start;
          }
          }
    #permit-information{
        display:none; 
      }

         </style>
       </head>
       <body>
        <div class="window-w-h">
          <div class="login-page">
            <div class="content-body-login">
              <header>
                <div class="header-content">
                  <img src="http://www.funplus.com/wp-content/themes/swiss/assets/img/logo.jpg" alt class="logo-img" />
                </div>

              </header>
              <section>
                <div class="section-content">
                  <div class="aside aside-left">
                    <div   class="login-bg"></div>
                    <p class="bg-tips">成为新一代全球互动娱乐领域的领袖</p>
                  </div>
                  <div class="aside aside-right">
                      <div class="login-con bgfff">
                        <ul class="login-content-head">
                          <li class="change-logintype item active" loginType='up'>账户登录</li>
                          <li class="change-logintype item " loginType='qr'>短信登录</li>
                          
                        </ul>
                      <!-- 用户名密码登录 -->
                      <div class="login-body">
                        
                        <div class="login-box active">
                          <form ref="loginForm" >
                            <div class="form-group">
                              <input type="text" class="form-control" id="username" word-key="userNamePlaceholder" placeholder="">
                            </div>
                            <div class="form-group">
                              <input type="password" class="form-control" id="password"  word-key="passwordPlaceholder" placeholder="">
                            </div>
                            <div class="form-group code-group"> 
                              <input type="text" class="form-control" id="captcha" word-key="captchaPlaceholder" placeholder="">
                              <span class="input-group-addon">
                                <img src="" alt="" id="captchaImg">
                              </span>
                            </div>
                             <p class="forget-password text-right"><a href="javascript:void(0)" word-key="forgetPassword" id="forgetPassword"></a></p>
                            <div class="form-group">
                              <button type="submit" id="btnLogin" class="btn btn-primary btn-block" word-key="loginBtn">
                                登录
                              </button>
                          </div>
                          </form>
                        </div>

                        <!-- 扫码登录 -->
                        <div  class="login-box">
                          <!-- <div class="qr-box">
                            <div id="ddtalk_login_container"></div>
                          </div> -->

                          <form ref="loginForm" >
                            <div class="form-group">
                              <input type="text" class="form-control" name="phoneNumber" id="phoneNumber" word-key="" placeholder="请输入电话号码">
                            </div>
                            <div class="form-group code-group">
                              <input type="text" class="form-control" id="SMScaptcha" name="SMScaptcha"  word-key="" placeholder="请输入验证码">
                              <span class="input-group-addon">
                                <img src="" alt="" id="captchaSMSImg">
                              </span>
                            </div>
                            <div class="form-group code-group"> 
                              <input type="text" class="form-control" id="SMScode" word-key="" placeholder="请输入短信验证码">
                              <span class="input-group-addon send-code" id="sendCodeBtn">
                                发送验证码
                              </span>
                            </div>
                            <div class="form-group">
                              <button type="submit" id="btnLoginSMS" class="btn btn-primary btn-block" word-key="loginBtn">
                                登录
                              </button>
                            </div>
                          </form>

                        </div>
                      </div>
                    </div>
                  </div>
                </div>
              </section>
              <footer class="permit-information"><div class="footer-content"><span data-v-7ba5bd90="">Copyright FunPlus 2020</span><span>公司网址: www.funplus.com</span></div></footer>
            </div>
          </div>
        </div>
      </body>
      <script src="@resourceServerDomain@/static/js/jquery.min.js"></script>
      <script src="@resourceServerDomain@/static/js/jquery.cookie.js"></script>
      <script src="@resourceServerDomain@/static/bootstrap/js/bootstrap.js"></script>
      <script src="@resourceServerDomain@/static/js/idaas-custom-login.js"></script>

      <script>
                window.onload=function(){
          var SMSEnterpriseAuthId='';
          var sendSMSCodeTime = 60;
          var sendSMSCodeTimer = null;
          var isSending = false
          var IDaaSLogin = new Weblogin({
            baseUrl:"@baseUrl@",
            client_id:"@client_id@",
            client_secret:"@client_secret@",
            enterpriseId:'@enterpriseId@',
            apiVersion:"@apiVersion@",
            pageWords:[
              {
                key : "qrTips",
                zh : "扫码登录更便捷",
                en : "Scan QR code to log on",
              },
              {
                key : "upTips",
                zh : "使用账号登录",
                en : "Enter account information to log on.",
              },{
                key : "userNamePlaceholder",
                zh : "请输入用户名、邮箱、手机号",
                en : "Enter a username, email, or phoneNumber",
              },{
                key : "passwordPlaceholder",
                zh : "请输入密码",
                en : "Enter the password",
              },{
                key : "captchaPlaceholder",
                zh  :  "请输入验证码",
                en : "Enter the captcha code",
              },{
                key : "forgetPassword",
                zh  :  "忘记密码",
                en : "Forgot password",
              },{
                key : "loginBtn",
                zh  : "登录",
                en : "Log On",
              }
            ]
          })
    //初始化页面
    function initPage() {
        // 获取默认图标，非必需，可引用外部图标
        $('#qrIcon').attr('src',IDaaSLogin.qrLoginBg());
        $('#upIcon').attr('src',IDaaSLogin.upLoginBg());

        //获取页面当前语言
        // var language = IDaaSLogin.getCurrentLanguage()
        // console.log(language)

        //获取公司信息 logo name等进行展示
        IDaaSLogin.getEnterpriseInfo(function (data) {
          $('#enterpriseLogo').attr('src','data:image/gif;base64,'+data.logo);
          $('#enterpriseName').html(data.fullName);
        });

      //获取公司认证源列表进行渲染，初始化三方认证源
      IDaaSLogin.getAdapters(function (data) {
        //找出dd认证源
        $.each(data.list,function(index,val){
          if(val.authId == 'sms'){
             SMSEnterpriseAuthId = val.enterpriseAuthId
          }
        })
      });

    }

    function getCaptcha(){
      IDaaSLogin.getCaptcha(function (captcha) {
        $('#captchaImg').attr('src','data:image/gif;base64,'+captcha.captcha);
      });

    }
 // 倒计时
    function reSendCode() {
        if(sendSMSCodeTime > 0) {
          clearInterval(sendSMSCodeTimer)
          sendSMSCodeTimer = setInterval(() => {
            if(sendSMSCodeTime == 1) {
              $("#sendCodeBtn").html('获取验证码')
              clearInterval(sendSMSCodeTimer)
              sendSMSCodeTime = 60
              return
            }
            sendSMSCodeTime--
            $("#sendCodeBtn").html(sendSMSCodeTime+'s')
            
          }, 1000);
        } else {
          sendSMSCodeTime = 60
          $("#sendCodeBtn").html('获取验证码')
        }
      }
    function getSMSCaptcha(){
      IDaaSLogin.getSmsCaptcha(function (captcha) {
        $('#captchaSMSImg').attr('src','data:image/gif;base64,'+captcha.captcha);
      });
    }

    function sendSMSCode(){
      var params ={
        phoneNumber : $("#phoneNumber").val(),
        captcha : $("#SMScaptcha").val(),
        enterpriseAuthId:SMSEnterpriseAuthId
      }
      if(!params.phoneNumber){
        IDaaSLogin.errorTips("手机号不能为空")
        return false;
      }
      if(!params.captcha){
        IDaaSLogin.errorTips("验证码不能为空")
        return false;
      }
      IDaaSLogin.sendSMSCode(params,function(result,err){
        isSending = false
        if(result){
          reSendCode()
        }else{
          IDaaSLogin.errorTips(err.errorMessage)
          getSMSCaptcha();
        }
      })
    }
    function submitSMSCode(){
      var params ={
        phoneNumber : $("#phoneNumber").val(),
        captcha : $("#SMScaptcha").val(),
        enterpriseAuthId:SMSEnterpriseAuthId,
        code : $("#SMScode").val()
      }
      IDaaSLogin.submitSmsCodeLogin(params,function(error){
        //这里处理失败时的状态
        console.log(error)
      })
    }


    function login() {
      var username = $('#username').val();
      var password = $('#password').val();
      var captcha = $('#captcha').val();
      if(username == ''){
        IDaaSLogin.errorTips("用户名不能为空")
      }else if(password == ''){
        IDaaSLogin.errorTips("密码不能为空")
      }else if(captcha == ''){
        IDaaSLogin.errorTips("验证码不能为空")
      }
      IDaaSLogin.signupAndLogin({
        username:username,
        password:password,
        captcha:captcha
      },function (err) {
        //登录错误回调函数，处理自动刷新验证码
        err && getCaptcha();
      });

    }

    initPage();
    getCaptcha();
    getSMSCaptcha();
    $('form').on('submit',function(e){
      e.preventDefault();
    })

    //登录功能
    $('#btnLogin').on('click',function (e) {
      e.preventDefault();
      login();
    });

    //语言切换
    $('.login-con-lang').on('click',function(){
      IDaaSLogin.setCurrentLanguage($(this).attr('language'))
    })
    //忘记密码
    $('#forgetPassword').on('click',function () {
      IDaaSLogin.forgetPassword();
    });
    //注册功能
    $('#register').on('click',function (e) {
      e.preventDefault()
      IDaaSLogin.register();
    });
    //刷新图片验证码
    $('#captchaImg').on('click',function () {
      getCaptcha();
    });
    //刷新短信登录图片验证码
    $('#captchaSMSImg').on('click',function () {
      getSMSCaptcha();
    });
    //发送短信验证码
    $('#sendCodeBtn').on('click',function () {
      //防止重复点击
      if(sendSMSCodeTime!=0 && isSending){
        return false
      }
      isSending = true
      sendSMSCode();
    });
    //短信登录提交
    $('#btnLoginSMS').on('click',function (e) {
      e.preventDefault();
      submitSMSCode();
    });
    
    //切换登录方式
    $('.change-logintype').on('click',function () {
      $('.change-logintype').toggleClass('active');
      $('.login-box').toggleClass('active');

    });


  }
</script>
</html>

```
#### 2、效果图：
![image.png](https://intranetproxy.alipay.com/skylark/lark/0/2020/png/263344/1602312401963-f02d5916-6c12-4f1f-ba6c-ee5f282dabdd.png#height=407&id=nT1Is&margin=%5Bobject%20Object%5D&name=image.png&originHeight=813&originWidth=1920&originalType=binary&ratio=1&size=718482&status=done&style=none&width=960)<br />

## 二、企业微信扫码登录认证源
#### 1、模板代码
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Title</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <link rel="stylesheet" href="@resourceServerDomain@/static/bootstrap/css/bootstrap.min.css">
  <link rel="stylesheet" type="text/css" href="@resourceServerDomain@/static/css/custom-page-style.css">
  <style>
        /*
            在这里写自定义样式

            */
           /*
            在这里写自定义样式

            */
          .window-w-h {
            width: 100%;
            height: 100%;
          }
          .window-w-h .login-page {
            height: 100%;
          }
          .content-body-login {
            height: 100%;
            display: flex;
            flex-direction: column;
          }
          .content-body-login header {
            height: 70px;
            width: 100%;
            border-bottom: 1px solid #F0F0F0;
          }
          .content-body-login header .header-content {
            height: 100%;
            width: 1100px;
            margin: 0 auto;
            display: flex;
            align-items: center;
          }
          .content-body-login header .header-content .logo-img {
            width: 172px ;
          }
          .content-body-login section {
            flex: 1;
          }
          .content-body-login section .section-content {
            width: 1100px;
            margin: 0 auto;
            display: flex;
            height: 100%;
            padding-bottom: 50px;
          }
          .content-body-login section .section-content .aside {
            width: 50%;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
          }
          .content-body-login section .section-content .aside-left {
            padding: 0 13px;
            display: flex;
            flex-direction: column;
          }
          .content-body-login section .section-content .aside-left .login-bg {
            width: 100%;
            height: 418px ;
            background: url(http://117.50.108.64:9911/frontend/login/img/login-bg.png) no-repeat center;
            background-size: cover ;
            position: relative;
          }
          .content-body-login section .section-content .aside-left .bg-tips {
            font-size: 18px;
            color: #fff;
            background-color: #766655;
            padding: 18px 15px ;
            letter-spacing: 2px;
            width: 100%;
          }
          .content-body-login section .section-content .aside-right .login-con {
            padding: 0;
            box-shadow: none;
            width: 350px;
          }
          .content-body-login section .section-content .aside-right .login-con .login-body {
            padding: 0;
            padding-top: 35px ;
          }
          .content-body-login section .section-content .aside-right .captcha-content {
            position: absolute;
            left: -51px;
            top: 8px;
          }
          .content-body-login section .section-content .aside-right .login-content-head {
            min-height: 64px;
            display: flex;
            position: relative;
            border-bottom: 1px solid #eee;
          }
          .content-body-login section .section-content .aside-right .login-content-head .item {
            width: 50%;
            text-align: center;
            display: inline-block;
            font-size: 16px;
            color: #666;
            padding: 20px 0;
            position: relative;
            cursor: pointer;
          }
          .content-body-login section .section-content .aside-right .login-content-head .item::before {
            content: "";
            position: absolute;
            width: 100%;
            height: 2px;
            bottom: 0;
            left: 0;
            background: #F39339;
            display: none;
          }
          .content-body-login section .section-content .aside-right .login-content-head .item:hover,
          .content-body-login section .section-content .aside-right .login-content-head .item.active {
            color: #F39339;
          }
          .content-body-login section .section-content .aside-right .login-content-head .item:hover::before,
          .content-body-login section .section-content .aside-right .login-content-head .item.active::before {
            display: block;
          }
          .content-body-login section .section-content .aside-right .forget_password {
            color: #F39339;
            cursor: pointer;
            font-size: 14px;
          }
          .content-body-login section .section-content .aside-right .forget_password:hover {
            color: #FA8117;
          }
          .content-body-login section .section-content .aside-right .qr-box {
            padding: 0;
          }
          .content-body-login section .section-content .aside-right .login-box {
            margin-bottom: 0;
            min-height: 330px;
            display: none;
          }
         .content-body-login section .section-content .aside-right .login-box.active{
          display: block;
         }
          .permit-information {
            width: 100%;      
            text-align: center;
            height: 50px;
            border-top: 1px solid #F0F0F0;
          }
    	  .login-page .qr-box{
    		border:none;
    	  }
          .permit-information .footer-content {
            height: 100%;
            width: 1100px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
          }
          .permit-information .footer-content span {
            font-size: 12px;
            color: #B7B7B7 ;
          }
          .input-group-addon{
            font-size: 12px;
            color: #338DD6;
            cursor: pointer;
            display: inline-block;
          }
          .login-page .login-body .code-group .input-group-addon{
            width: 108px;
          }
          .form-control:-webkit-autofill{
            box-shadow: 0 0 0px 1000px white inset !important;
          }
          @media (max-width: 1020px) {
            .permit-information .footer-content {
              width: auto;
              padding: 0 15px;
            }
          }

          @media (max-width: 1020px) {
          .login-page .content-body-login .header-content,
            .login-page .content-body-login .section-content {
              width: auto;
          }
          .login-page .content-body-login .header-content {
              justify-content: center;
          }
          .login-page .content-body-login .section-content .aside-left {
              width: 0;
              display: none;
          }
          .login-page .content-body-login .section-content .aside-right {
              width: 100%;
              padding-top: 50px;
          }
          .login-page .content-body-login .section-content .aside {
              justify-content: flex-start;
          }
          }
    #permit-information{
        display:none; 
      }

         </style>
       </head>
       <body>
        <div class="window-w-h">
          <div class="login-page">
            <div class="content-body-login">
              <header>
                <div class="header-content">
                  <img src="http://www.funplus.com/wp-content/themes/swiss/assets/img/logo.jpg" alt class="logo-img" />
                </div>

              </header>
              <section>
                <div class="section-content">
                  <div class="aside aside-left">
                    <div   class="login-bg"></div>
                    <p class="bg-tips">成为新一代全球互动娱乐领域的领袖</p>
                  </div>
                  <div class="aside aside-right">
                      <div class="login-con bgfff">
                        <ul class="login-content-head">
                          <li class="change-logintype item active" loginType='up'>账户登录</li>
                          <li class="change-logintype item " loginType='qr'>扫码登录</li>
                          
                        </ul>
                      <!-- 用户名密码登录 -->
                      <div class="login-body">
                        
                        <div class="login-box active">
                          <form ref="loginForm" >
                            <div class="form-group">
                              <input type="text" class="form-control" id="username" word-key="userNamePlaceholder" placeholder="">
                            </div>
                            <div class="form-group">
                              <input type="password" class="form-control" id="password"  word-key="passwordPlaceholder" placeholder="">
                            </div>
                            <div class="form-group code-group"> 
                              <input type="text" class="form-control" id="captcha" word-key="captchaPlaceholder" placeholder="">
                              <span class="input-group-addon">
                                <img src="" alt="" id="captchaImg">
                              </span>
                            </div>
                             <p class="forget-password text-right"><a href="javascript:void(0)" word-key="forgetPassword" id="forgetPassword"></a></p>
                            <div class="form-group">
                              <button type="submit" id="btnLogin" class="btn btn-primary btn-block" word-key="loginBtn">
                                登录
                              </button>
                          </div>
                          </form>
                        </div>

                        <!-- 扫码登录 -->
                        <div  class="login-box">
                           <div class="qr-box">
                            <div id="enterpri_wechat_login_container"></div>
                          </div>

                          <!--<form ref="loginForm" >
                            <div class="form-group">
                              <input type="text" class="form-control" name="phoneNumber" id="phoneNumber" word-key="" placeholder="请输入电话号码">
                            </div>
                            <div class="form-group code-group">
                              <input type="text" class="form-control" id="SMScaptcha" name="SMScaptcha"  word-key="" placeholder="请输入验证码">
                              <span class="input-group-addon">
                                <img src="" alt="" id="captchaSMSImg">
                              </span>
                            </div>
                            <div class="form-group code-group"> 
                              <input type="text" class="form-control" id="SMScode" word-key="" placeholder="请输入短信验证码">
                              <span class="input-group-addon send-code" id="sendCodeBtn">
                                发送验证码
                              </span>
                            </div>
                            <div class="form-group">
                              <button type="submit" id="btnLoginSMS" class="btn btn-primary btn-block" word-key="loginBtn">
                                登录
                              </button>
                            </div>
                          </form>-->

                        </div>
                      </div>
                    </div>
                  </div>
                </div>
              </section>
              <footer class="permit-information"><div class="footer-content"><span data-v-7ba5bd90="">Copyright FunPlus 2020</span><span>公司网址: www.funplus.com</span></div></footer>
            </div>
          </div>
        </div>
      </body>
      <script src="@resourceServerDomain@/static/js/jquery.min.js"></script>
      <script src="@resourceServerDomain@/static/js/jquery.cookie.js"></script>
      <script src="@resourceServerDomain@/static/bootstrap/js/bootstrap.js"></script>
      <script src="@resourceServerDomain@/static/js/idaas-custom-login.js"></script>

      <script>
                window.onload=function(){
          var SMSEnterpriseAuthId='';
          var sendSMSCodeTime = 60;
          var sendSMSCodeTimer = null;
          var isSending = false
          var IDaaSLogin = new Weblogin({
            baseUrl:"@baseUrl@",
            client_id:"@client_id@",
            client_secret:"@client_secret@",
            enterpriseId:'@enterpriseId@',
            apiVersion:"@apiVersion@",
            pageWords:[
              {
                key : "qrTips",
                zh : "扫码登录更便捷",
                en : "Scan QR code to log on",
              },
              {
                key : "upTips",
                zh : "使用账号登录",
                en : "Enter account information to log on.",
              },{
                key : "userNamePlaceholder",
                zh : "请输入用户名、邮箱、手机号",
                en : "Enter a username, email, or phoneNumber",
              },{
                key : "passwordPlaceholder",
                zh : "请输入密码",
                en : "Enter the password",
              },{
                key : "captchaPlaceholder",
                zh  :  "请输入验证码",
                en : "Enter the captcha code",
              },{
                key : "forgetPassword",
                zh  :  "忘记密码",
                en : "Forgot password",
              },{
                key : "loginBtn",
                zh  : "登录",
                en : "Log On",
              }
            ]
          })
    //初始化页面
    function initPage() {
        // 获取默认图标，非必需，可引用外部图标
        $('#qrIcon').attr('src',IDaaSLogin.qrLoginBg());
        $('#upIcon').attr('src',IDaaSLogin.upLoginBg());

        //获取页面当前语言
        // var language = IDaaSLogin.getCurrentLanguage()
        // console.log(language)

        //获取公司信息 logo name等进行展示
        IDaaSLogin.getEnterpriseInfo(function (data) {
          $('#enterpriseLogo').attr('src','data:image/gif;base64,'+data.logo);
          $('#enterpriseName').html(data.fullName);
        });

      //获取公司认证源列表进行渲染，初始化三方认证源
      IDaaSLogin.getAdapters(function (data) {
        //找出dd认证源
        $.each(data.list,function(index,val){

          if(val.authId == 'wechat_enterprise'){
             let styleConfig = {
               id:"enterpri_wechat_login_container",
             }
             IDaaSLogin.initEnterpriseWechatAdapter(val,styleConfig)
          }
        })
      });

    }

    function getCaptcha(){
      IDaaSLogin.getCaptcha(function (captcha) {
        $('#captchaImg').attr('src','data:image/gif;base64,'+captcha.captcha);
      });

    }
 
    function login() {
      var username = $('#username').val();
      var password = $('#password').val();
      var captcha = $('#captcha').val();
      if(username == ''){
        IDaaSLogin.errorTips("用户名不能为空")
      }else if(password == ''){
        IDaaSLogin.errorTips("密码不能为空")
      }else if(captcha == ''){
        IDaaSLogin.errorTips("验证码不能为空")
      }
      IDaaSLogin.signupAndLogin({
        username:username,
        password:password,
        captcha:captcha
      },function (err) {
        //登录错误回调函数，处理自动刷新验证码
        err && getCaptcha();
      });

    }

  

    initPage();
    getCaptcha();
    $('form').on('submit',function(e){
      e.preventDefault();
    })

    //登录功能
    $('#btnLogin').on('click',function (e) {
      e.preventDefault();
      login();
    });

    //语言切换
    $('.login-con-lang').on('click',function(){
      IDaaSLogin.setCurrentLanguage($(this).attr('language'))
    })
    //忘记密码
    $('#forgetPassword').on('click',function () {
      IDaaSLogin.forgetPassword();
    });
    //注册功能
    $('#register').on('click',function (e) {
      e.preventDefault()
      IDaaSLogin.register();
    });
    //刷新图片验证码
    $('#captchaImg').on('click',function () {
      getCaptcha();
    }); 
    //切换登录方式
    $('.change-logintype').on('click',function () {
      $('.change-logintype').toggleClass('active');
      $('.login-box').toggleClass('active');

    });


  }
</script>
</html>

```
#### 2、效果图
![image.png](https://intranetproxy.alipay.com/skylark/lark/0/2020/png/263344/1602311944955-d1ce8b22-58eb-4827-8b05-090e1eb73905.png#height=452&id=dAmVI&margin=%5Bobject%20Object%5D&name=image.png&originHeight=903&originWidth=1920&originalType=binary&ratio=1&size=742615&status=done&style=none&width=960)
## 三、钉钉扫码登录认证源
#### 1、模板代码
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Title</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <link rel="stylesheet" href="@resourceServerDomain@/static/bootstrap/css/bootstrap.min.css">
  <link rel="stylesheet" type="text/css" href="@resourceServerDomain@/static/css/custom-page-style.css">
  <style>
        /*
            在这里写自定义样式

            */
           /*
            在这里写自定义样式

            */
          .window-w-h {
            width: 100%;
            height: 100%;
          }
          .window-w-h .login-page {
            height: 100%;
          }
          .content-body-login {
            height: 100%;
            display: flex;
            flex-direction: column;
          }
          .content-body-login header {
            height: 70px;
            width: 100%;
            border-bottom: 1px solid #F0F0F0;
          }
          .content-body-login header .header-content {
            height: 100%;
            width: 1100px;
            margin: 0 auto;
            display: flex;
            align-items: center;
          }
          .content-body-login header .header-content .logo-img {
            width: 172px ;
          }
          .content-body-login section {
            flex: 1;
          }
          .content-body-login section .section-content {
            width: 1100px;
            margin: 0 auto;
            display: flex;
            height: 100%;
            padding-bottom: 50px;
          }
          .content-body-login section .section-content .aside {
            width: 50%;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
          }
          .content-body-login section .section-content .aside-left {
            padding: 0 13px;
            display: flex;
            flex-direction: column;
          }
          .content-body-login section .section-content .aside-left .login-bg {
            width: 100%;
            height: 418px ;
            background: url(http://117.50.108.64:9911/frontend/login/img/login-bg.png) no-repeat center;
            background-size: cover ;
            position: relative;
          }
          .content-body-login section .section-content .aside-left .bg-tips {
            font-size: 18px;
            color: #fff;
            background-color: #766655;
            padding: 18px 15px ;
            letter-spacing: 2px;
            width: 100%;
          }
          .content-body-login section .section-content .aside-right .login-con {
            padding: 0;
            box-shadow: none;
            width: 350px;
          }
          .content-body-login section .section-content .aside-right .login-con .login-body {
            padding: 0;
            padding-top: 35px ;
          }
          .content-body-login section .section-content .aside-right .captcha-content {
            position: absolute;
            left: -51px;
            top: 8px;
          }
          .content-body-login section .section-content .aside-right .login-content-head {
            min-height: 64px;
            display: flex;
            position: relative;
            border-bottom: 1px solid #eee;
          }
          .content-body-login section .section-content .aside-right .login-content-head .item {
            width: 50%;
            text-align: center;
            display: inline-block;
            font-size: 16px;
            color: #666;
            padding: 20px 0;
            position: relative;
            cursor: pointer;
          }
          .content-body-login section .section-content .aside-right .login-content-head .item::before {
            content: "";
            position: absolute;
            width: 100%;
            height: 2px;
            bottom: 0;
            left: 0;
            background: #F39339;
            display: none;
          }
          .content-body-login section .section-content .aside-right .login-content-head .item:hover,
          .content-body-login section .section-content .aside-right .login-content-head .item.active {
            color: #F39339;
          }
          .content-body-login section .section-content .aside-right .login-content-head .item:hover::before,
          .content-body-login section .section-content .aside-right .login-content-head .item.active::before {
            display: block;
          }
          .content-body-login section .section-content .aside-right .forget_password {
            color: #F39339;
            cursor: pointer;
            font-size: 14px;
          }
          .content-body-login section .section-content .aside-right .forget_password:hover {
            color: #FA8117;
          }
          .content-body-login section .section-content .aside-right .qr-box {
            padding: 0;
          }
          .content-body-login section .section-content .aside-right .login-box {
            margin-bottom: 0;
            min-height: 330px;
            display: none;
          }
         .content-body-login section .section-content .aside-right .login-box.active{
          display: block;
         }
    	.login-page .qr-box{border:none;}
          .permit-information {
            width: 100%;      
            text-align: center;
            height: 50px;
            border-top: 1px solid #F0F0F0;
          }
          .permit-information .footer-content {
            height: 100%;
            width: 1100px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
          }
          .permit-information .footer-content span {
            font-size: 12px;
            color: #B7B7B7 ;
          }
          .input-group-addon{
            font-size: 12px;
            color: #338DD6;
            cursor: pointer;
            display: inline-block;
          }
          .login-page .login-body .code-group .input-group-addon{
            width: 108px;
          }
          .form-control:-webkit-autofill{
            box-shadow: 0 0 0px 1000px white inset !important;
          }
          @media (max-width: 1020px) {
            .permit-information .footer-content {
              width: auto;
              padding: 0 15px;
            }
          }

          @media (max-width: 1020px) {
          .login-page .content-body-login .header-content,
            .login-page .content-body-login .section-content {
              width: auto;
          }
          .login-page .content-body-login .header-content {
              justify-content: center;
          }
          .login-page .content-body-login .section-content .aside-left {
              width: 0;
              display: none;
          }
          .login-page .content-body-login .section-content .aside-right {
              width: 100%;
              padding-top: 50px;
          }
          .login-page .content-body-login .section-content .aside {
              justify-content: flex-start;
          }
          }
    #permit-information{
        display:none; 
      }

         </style>
       </head>
       <body>
        <div class="window-w-h">
          <div class="login-page">
            <div class="content-body-login">
              <header>
                <div class="header-content">
                  <img src="http://www.funplus.com/wp-content/themes/swiss/assets/img/logo.jpg" alt class="logo-img" />
                </div>

              </header>
              <section>
                <div class="section-content">
                  <div class="aside aside-left">
                    <div   class="login-bg"></div>
                    <p class="bg-tips">成为新一代全球互动娱乐领域的领袖</p>
                  </div>
                  <div class="aside aside-right">
                      <div class="login-con bgfff">
                        <ul class="login-content-head">
                          <li class="change-logintype item active" loginType='up'>账户登录</li>
                          <li class="change-logintype item " loginType='qr'>扫码登录</li>
                          
                        </ul>
                      <!-- 用户名密码登录 -->
                      <div class="login-body">
                        
                        <div class="login-box active">
                          <form ref="loginForm" >
                            <div class="form-group">
                              <input type="text" class="form-control" id="username" word-key="userNamePlaceholder" placeholder="">
                            </div>
                            <div class="form-group">
                              <input type="password" class="form-control" id="password"  word-key="passwordPlaceholder" placeholder="">
                            </div>
                            <div class="form-group code-group"> 
                              <input type="text" class="form-control" id="captcha" word-key="captchaPlaceholder" placeholder="">
                              <span class="input-group-addon">
                                <img src="" alt="" id="captchaImg">
                              </span>
                            </div>
                             <p class="forget-password text-right"><a href="javascript:void(0)" word-key="forgetPassword" id="forgetPassword"></a></p>
                            <div class="form-group">
                              <button type="submit" id="btnLogin" class="btn btn-primary btn-block" word-key="loginBtn">
                                登录
                              </button>
                          </div>
                          </form>
                        </div>

                        <!-- 扫码登录 -->
                        <div  class="login-box">
                           <div class="qr-box">
                            <div id="ddtalk_login_container"></div>
                          </div> 
<!--
                          <form ref="loginForm" >
                            <div class="form-group">
                              <input type="text" class="form-control" name="phoneNumber" id="phoneNumber" word-key="" placeholder="请输入电话号码">
                            </div>
                            <div class="form-group code-group">
                              <input type="text" class="form-control" id="SMScaptcha" name="SMScaptcha"  word-key="" placeholder="请输入验证码">
                              <span class="input-group-addon">
                                <img src="" alt="" id="captchaSMSImg">
                              </span>
                            </div>
                            <div class="form-group code-group"> 
                              <input type="text" class="form-control" id="SMScode" word-key="" placeholder="请输入短信验证码">
                              <span class="input-group-addon send-code" id="sendCodeBtn">
                                发送验证码
                              </span>
                            </div>
                            <div class="form-group">
                              <button type="submit" id="btnLoginSMS" class="btn btn-primary btn-block" word-key="loginBtn">
                                登录
                              </button>
                            </div>
                          </form>-->

                        </div>
                      </div>
                    </div>
                  </div>
                </div>
              </section>
              <footer class="permit-information"><div class="footer-content"><span data-v-7ba5bd90="">Copyright FunPlus 2020</span><span>公司网址: www.funplus.com</span></div></footer>
            </div>
          </div>
        </div>
      </body>
      <script src="@resourceServerDomain@/static/js/jquery.min.js"></script>
      <script src="@resourceServerDomain@/static/js/jquery.cookie.js"></script>
      <script src="@resourceServerDomain@/static/bootstrap/js/bootstrap.js"></script>
      <script src="@resourceServerDomain@/static/js/idaas-custom-login.js"></script>

      <script>
                window.onload=function(){
          var SMSEnterpriseAuthId='';
          var sendSMSCodeTime = 60;
          var sendSMSCodeTimer = null;
          var isSending = false
          var IDaaSLogin = new Weblogin({
            baseUrl:"@baseUrl@",
            client_id:"@client_id@",
            client_secret:"@client_secret@",
            enterpriseId:'@enterpriseId@',
            apiVersion:"@apiVersion@",
            pageWords:[
              {
                key : "qrTips",
                zh : "扫码登录更便捷",
                en : "Scan QR code to log on",
              },
              {
                key : "upTips",
                zh : "使用账号登录",
                en : "Enter account information to log on.",
              },{
                key : "userNamePlaceholder",
                zh : "请输入用户名、邮箱、手机号",
                en : "Enter a username, email, or phoneNumber",
              },{
                key : "passwordPlaceholder",
                zh : "请输入密码",
                en : "Enter the password",
              },{
                key : "captchaPlaceholder",
                zh  :  "请输入验证码",
                en : "Enter the captcha code",
              },{
                key : "forgetPassword",
                zh  :  "忘记密码",
                en : "Forgot password",
              },{
                key : "loginBtn",
                zh  : "登录",
                en : "Log On",
              }
            ]
          })
    //初始化页面
    function initPage() {
        // 获取默认图标，非必需，可引用外部图标
        $('#qrIcon').attr('src',IDaaSLogin.qrLoginBg());
        $('#upIcon').attr('src',IDaaSLogin.upLoginBg());

        //获取页面当前语言
        // var language = IDaaSLogin.getCurrentLanguage()
        // console.log(language)

        //获取公司信息 logo name等进行展示
        IDaaSLogin.getEnterpriseInfo(function (data) {
          $('#enterpriseLogo').attr('src','data:image/gif;base64,'+data.logo);
          $('#enterpriseName').html(data.fullName);
        });

      //获取公司认证源列表进行渲染，初始化三方认证源
      IDaaSLogin.getAdapters(function (data) {
        //找出dd认证源
        $.each(data.list,function(index,val){
           if(val.authId == 'ddtalk'){
             let styleConfig = {
               id:"ddtalk_login_container",
               width:'300',
               height:'300'
             }
             IDaaSLogin.initDDtalkAdapter(val,styleConfig)
           }
          
        })
      });

    }

    function getCaptcha(){
      IDaaSLogin.getCaptcha(function (captcha) {
        $('#captchaImg').attr('src','data:image/gif;base64,'+captcha.captcha);
      });

    }

    function login() {
      var username = $('#username').val();
      var password = $('#password').val();
      var captcha = $('#captcha').val();
      if(username == ''){
        IDaaSLogin.errorTips("用户名不能为空")
      }else if(password == ''){
        IDaaSLogin.errorTips("密码不能为空")
      }else if(captcha == ''){
        IDaaSLogin.errorTips("验证码不能为空")
      }
      IDaaSLogin.signupAndLogin({
        username:username,
        password:password,
        captcha:captcha
      },function (err) {
        //登录错误回调函数，处理自动刷新验证码
        err && getCaptcha();
      });

    }

 
    initPage();
    getCaptcha();
    $('form').on('submit',function(e){
      e.preventDefault();
    })

    //登录功能
    $('#btnLogin').on('click',function (e) {
      e.preventDefault();
      login();
    });

    //语言切换
    $('.login-con-lang').on('click',function(){
      IDaaSLogin.setCurrentLanguage($(this).attr('language'))
    })
    //忘记密码
    $('#forgetPassword').on('click',function () {
      IDaaSLogin.forgetPassword();
    });
    //注册功能
    $('#register').on('click',function (e) {
      e.preventDefault()
      IDaaSLogin.register();
    });
    //刷新图片验证码
    $('#captchaImg').on('click',function () {
      getCaptcha();
    });
 
  
    
    //切换登录方式
    $('.change-logintype').on('click',function () {
      $('.change-logintype').toggleClass('active');
      $('.login-box').toggleClass('active');

    });


  }
</script>
</html>

```
#### 2、效果图
![image.png](https://intranetproxy.alipay.com/skylark/lark/0/2020/png/263344/1602313163179-43011c42-6eb0-4d33-90c4-06bfc57d1aa9.png#height=452&id=sBBA3&margin=%5Bobject%20Object%5D&name=image.png&originHeight=903&originWidth=1920&originalType=binary&ratio=1&size=754992&status=done&style=none&width=960)<br />​<br />
## 四、微信扫码登录认证源
​<br />
#### 1、模板代码
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Title</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <link rel="stylesheet" href="@resourceServerDomain@/static/bootstrap/css/bootstrap.min.css">
  <link rel="stylesheet" type="text/css" href="@resourceServerDomain@/static/css/custom-page-style.css">
  <style>
        /*
            在这里写自定义样式

            */
           /*
            在这里写自定义样式

            */
          .window-w-h {
            width: 100%;
            height: 100%;
          }
          .window-w-h .login-page {
            height: 100%;
          }
          .content-body-login {
            height: 100%;
            display: flex;
            flex-direction: column;
          }
          .content-body-login header {
            height: 70px;
            width: 100%;
            border-bottom: 1px solid #F0F0F0;
          }
          .content-body-login header .header-content {
            height: 100%;
            width: 1100px;
            margin: 0 auto;
            display: flex;
            align-items: center;
          }
          .content-body-login header .header-content .logo-img {
            width: 172px ;
          }
          .content-body-login section {
            flex: 1;
          }
          .content-body-login section .section-content {
            width: 1100px;
            margin: 0 auto;
            display: flex;
            height: 100%;
            padding-bottom: 50px;
          }
          .content-body-login section .section-content .aside {
            width: 50%;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
          }
          .content-body-login section .section-content .aside-left {
            padding: 0 13px;
            display: flex;
            flex-direction: column;
          }
          .content-body-login section .section-content .aside-left .login-bg {
            width: 100%;
            height: 418px ;
            background: url(http://117.50.108.64:9911/frontend/login/img/login-bg.png) no-repeat center;
            background-size: cover ;
            position: relative;
          }
          .content-body-login section .section-content .aside-left .bg-tips {
            font-size: 18px;
            color: #fff;
            background-color: #766655;
            padding: 18px 15px ;
            letter-spacing: 2px;
            width: 100%;
          }
          .content-body-login section .section-content .aside-right .login-con {
            padding: 0;
            box-shadow: none;
            width: 350px;
          }
          .content-body-login section .section-content .aside-right .login-con .login-body {
            padding: 0;
            padding-top: 35px ;
          }
          .content-body-login section .section-content .aside-right .captcha-content {
            position: absolute;
            left: -51px;
            top: 8px;
          }
          .content-body-login section .section-content .aside-right .login-content-head {
            min-height: 64px;
            display: flex;
            position: relative;
            border-bottom: 1px solid #eee;
          }
          .content-body-login section .section-content .aside-right .login-content-head .item {
            width: 50%;
            text-align: center;
            display: inline-block;
            font-size: 16px;
            color: #666;
            padding: 20px 0;
            position: relative;
            cursor: pointer;
          }
          .content-body-login section .section-content .aside-right .login-content-head .item::before {
            content: "";
            position: absolute;
            width: 100%;
            height: 2px;
            bottom: 0;
            left: 0;
            background: #F39339;
            display: none;
          }
          .content-body-login section .section-content .aside-right .login-content-head .item:hover,
          .content-body-login section .section-content .aside-right .login-content-head .item.active {
            color: #F39339;
          }
          .content-body-login section .section-content .aside-right .login-content-head .item:hover::before,
          .content-body-login section .section-content .aside-right .login-content-head .item.active::before {
            display: block;
          }
          .content-body-login section .section-content .aside-right .forget_password {
            color: #F39339;
            cursor: pointer;
            font-size: 14px;
          }
          .content-body-login section .section-content .aside-right .forget_password:hover {
            color: #FA8117;
          }
          .content-body-login section .section-content .aside-right .qr-box {
            padding: 0;
          }
          .content-body-login section .section-content .aside-right .login-box {
            margin-bottom: 0;
            min-height: 330px;
            display: none;
          }
         .content-body-login section .section-content .aside-right .login-box.active{
          display: block;
         }
    	.login-page .qr-box{border:none;}
          .permit-information {
            width: 100%;      
            text-align: center;
            height: 50px;
            border-top: 1px solid #F0F0F0;
          }
          .permit-information .footer-content {
            height: 100%;
            width: 1100px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
          }
          .permit-information .footer-content span {
            font-size: 12px;
            color: #B7B7B7 ;
          }
          .input-group-addon{
            font-size: 12px;
            color: #338DD6;
            cursor: pointer;
            display: inline-block;
          }
          .login-page .login-body .code-group .input-group-addon{
            width: 108px;
          }
          .form-control:-webkit-autofill{
            box-shadow: 0 0 0px 1000px white inset !important;
          }
          @media (max-width: 1020px) {
            .permit-information .footer-content {
              width: auto;
              padding: 0 15px;
            }
          }

          @media (max-width: 1020px) {
          .login-page .content-body-login .header-content,
            .login-page .content-body-login .section-content {
              width: auto;
          }
          .login-page .content-body-login .header-content {
              justify-content: center;
          }
          .login-page .content-body-login .section-content .aside-left {
              width: 0;
              display: none;
          }
          .login-page .content-body-login .section-content .aside-right {
              width: 100%;
              padding-top: 50px;
          }
          .login-page .content-body-login .section-content .aside {
              justify-content: flex-start;
          }
          }
    #permit-information{
        display:none; 
      }

         </style>
       </head>
       <body>
        <div class="window-w-h">
          <div class="login-page">
            <div class="content-body-login">
              <header>
                <div class="header-content">
                  <img src="http://www.funplus.com/wp-content/themes/swiss/assets/img/logo.jpg" alt class="logo-img" />
                </div>

              </header>
              <section>
                <div class="section-content">
                  <div class="aside aside-left">
                    <div   class="login-bg"></div>
                    <p class="bg-tips">成为新一代全球互动娱乐领域的领袖</p>
                  </div>
                  <div class="aside aside-right">
                      <div class="login-con bgfff">
                        <ul class="login-content-head">
                          <li class="change-logintype item active" loginType='up'>账户登录</li>
                          <li class="change-logintype item " loginType='qr'>扫码登录</li>
                          
                        </ul>
                      <!-- 用户名密码登录 -->
                      <div class="login-body">
                        
                        <div class="login-box active">
                          <form ref="loginForm" >
                            <div class="form-group">
                              <input type="text" class="form-control" id="username" word-key="userNamePlaceholder" placeholder="">
                            </div>
                            <div class="form-group">
                              <input type="password" class="form-control" id="password"  word-key="passwordPlaceholder" placeholder="">
                            </div>
                            <div class="form-group code-group"> 
                              <input type="text" class="form-control" id="captcha" word-key="captchaPlaceholder" placeholder="">
                              <span class="input-group-addon">
                                <img src="" alt="" id="captchaImg">
                              </span>
                            </div>
                             <p class="forget-password text-right"><a href="javascript:void(0)" word-key="forgetPassword" id="forgetPassword"></a></p>
                            <div class="form-group">
                              <button type="submit" id="btnLogin" class="btn btn-primary btn-block" word-key="loginBtn">
                                登录
                              </button>
                          </div>
                          </form>
                        </div>

                        <!-- 扫码登录 -->
                        <div  class="login-box">
                           <div class="qr-box">
                            <div id="ddtalk_login_container"></div>
                          </div> 
<!--
                          <form ref="loginForm" >
                            <div class="form-group">
                              <input type="text" class="form-control" name="phoneNumber" id="phoneNumber" word-key="" placeholder="请输入电话号码">
                            </div>
                            <div class="form-group code-group">
                              <input type="text" class="form-control" id="SMScaptcha" name="SMScaptcha"  word-key="" placeholder="请输入验证码">
                              <span class="input-group-addon">
                                <img src="" alt="" id="captchaSMSImg">
                              </span>
                            </div>
                            <div class="form-group code-group"> 
                              <input type="text" class="form-control" id="SMScode" word-key="" placeholder="请输入短信验证码">
                              <span class="input-group-addon send-code" id="sendCodeBtn">
                                发送验证码
                              </span>
                            </div>
                            <div class="form-group">
                              <button type="submit" id="btnLoginSMS" class="btn btn-primary btn-block" word-key="loginBtn">
                                登录
                              </button>
                            </div>
                          </form>-->

                        </div>
                      </div>
                    </div>
                  </div>
                </div>
              </section>
              <footer class="permit-information"><div class="footer-content"><span data-v-7ba5bd90="">Copyright FunPlus 2020</span><span>公司网址: www.funplus.com</span></div></footer>
            </div>
          </div>
        </div>
      </body>
      <script src="@resourceServerDomain@/static/js/jquery.min.js"></script>
      <script src="@resourceServerDomain@/static/js/jquery.cookie.js"></script>
      <script src="@resourceServerDomain@/static/bootstrap/js/bootstrap.js"></script>
      <script src="@resourceServerDomain@/static/js/idaas-custom-login.js"></script>

      <script>
                window.onload=function(){
          var SMSEnterpriseAuthId='';
          var sendSMSCodeTime = 60;
          var sendSMSCodeTimer = null;
          var isSending = false
          var IDaaSLogin = new Weblogin({
            baseUrl:"@baseUrl@",
            client_id:"@client_id@",
            client_secret:"@client_secret@",
            enterpriseId:'@enterpriseId@',
            apiVersion:"@apiVersion@",
            pageWords:[
              {
                key : "qrTips",
                zh : "扫码登录更便捷",
                en : "Scan QR code to log on",
              },
              {
                key : "upTips",
                zh : "使用账号登录",
                en : "Enter account information to log on.",
              },{
                key : "userNamePlaceholder",
                zh : "请输入用户名、邮箱、手机号",
                en : "Enter a username, email, or phoneNumber",
              },{
                key : "passwordPlaceholder",
                zh : "请输入密码",
                en : "Enter the password",
              },{
                key : "captchaPlaceholder",
                zh  :  "请输入验证码",
                en : "Enter the captcha code",
              },{
                key : "forgetPassword",
                zh  :  "忘记密码",
                en : "Forgot password",
              },{
                key : "loginBtn",
                zh  : "登录",
                en : "Log On",
              }
            ]
          })
    //初始化页面
    function initPage() {
        // 获取默认图标，非必需，可引用外部图标
        $('#qrIcon').attr('src',IDaaSLogin.qrLoginBg());
        $('#upIcon').attr('src',IDaaSLogin.upLoginBg());

        //获取页面当前语言
        // var language = IDaaSLogin.getCurrentLanguage()
        // console.log(language)

        //获取公司信息 logo name等进行展示
        IDaaSLogin.getEnterpriseInfo(function (data) {
          $('#enterpriseLogo').attr('src','data:image/gif;base64,'+data.logo);
          $('#enterpriseName').html(data.fullName);
        });

      //获取公司认证源列表进行渲染，初始化三方认证源
      IDaaSLogin.getAdapters(function (data) {
        //找出dd认证源
        $.each(data.list,function(index,val){
           if(val.authId == 'wechat'){
             let styleConfig = {
               id:"ddtalk_login_container",
               width:'300',
               height:'300'
             }
             IDaaSLogin.initWechatAdapter(val,styleConfig)
           }
          
        })
      });

    }

    function getCaptcha(){
      IDaaSLogin.getCaptcha(function (captcha) {
        $('#captchaImg').attr('src','data:image/gif;base64,'+captcha.captcha);
      });

    }

    function login() {
      var username = $('#username').val();
      var password = $('#password').val();
      var captcha = $('#captcha').val();
      if(username == ''){
        IDaaSLogin.errorTips("用户名不能为空")
      }else if(password == ''){
        IDaaSLogin.errorTips("密码不能为空")
      }else if(captcha == ''){
        IDaaSLogin.errorTips("验证码不能为空")
      }
      IDaaSLogin.signupAndLogin({
        username:username,
        password:password,
        captcha:captcha
      },function (err) {
        //登录错误回调函数，处理自动刷新验证码
        err && getCaptcha();
      });

    }

 
    initPage();
    getCaptcha();
    $('form').on('submit',function(e){
      e.preventDefault();
    })

    //登录功能
    $('#btnLogin').on('click',function (e) {
      e.preventDefault();
      login();
    });

    //语言切换
    $('.login-con-lang').on('click',function(){
      IDaaSLogin.setCurrentLanguage($(this).attr('language'))
    })
    //忘记密码
    $('#forgetPassword').on('click',function () {
      IDaaSLogin.forgetPassword();
    });
    //注册功能
    $('#register').on('click',function (e) {
      e.preventDefault()
      IDaaSLogin.register();
    });
    //刷新图片验证码
    $('#captchaImg').on('click',function () {
      getCaptcha();
    });
 
  
    
    //切换登录方式
    $('.change-logintype').on('click',function () {
      $('.change-logintype').toggleClass('active');
      $('.login-box').toggleClass('active');

    });


  }
</script>
</html>

```
#### 2、效果图![image.png](https://intranetproxy.alipay.com/skylark/lark/0/2020/png/263344/1602322358991-cc421a16-66b3-466d-82d8-d1d53d12ccae.png#height=903&id=a6nHH&margin=%5Bobject%20Object%5D&name=image.png&originHeight=903&originWidth=1920&originalType=binary&ratio=1&size=756131&status=done&style=none&width=1920)
