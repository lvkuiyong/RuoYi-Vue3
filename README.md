```
# 安装依赖
yarn --registry=https://registry.npmmirror.com
# 启动服务
yarn dev
```

## 地址

如参数管理，后台地址配置`@RequestMapping("/system/config")`对应参数管理`url`为`/system/config`

## 数据权限

权限标识配置不对在`菜单管理`配置好权限标识（菜单&按钮）

1. 确认此用户是否已经配置角色
2. 确认此角色是否已经配置菜单权限
3. 确认此菜单权限标识是否和后台代码一致

如参数管理
后台配置`@RequiresPermissions("system:config:view")`对应参数管理权限标识为`system:config:view`

注：如需要角色权限，配置角色权限字符 使用`@RequiresRoles("admin")`

## 图标使用

项目默认使用了`Font Awesome`和`Glyphicons`字体图标。

`Font Awesome` 默认图标示例代码 [@/demo/icon/fontawesome.html(opens new window)](https://gitee.com/y_project/RuoYi/blob/master/ruoyi-admin/src/main/resources/templates/demo/icon/fontawesome.html)
`Glyphicons` 默认图标示例代码 [@/demo/icon/glyphicons.html(opens new window)](https://gitee.com/y_project/RuoYi/blob/master/ruoyi-admin/src/main/resources/templates/demo/icon/glyphicons.html)

两者都可以在项目中任意地方使用。

Font Awesome 使用方式

```html
<!-- class 为 fontawesome 图标的名字 -->
<i class="fa fa-music"></i>
```

Glyphicons 使用方式

```html
<!-- class 为 glyphicons 图标的名字 -->
<i class="glyphicon glyphicon-music"></i>
```

## 系统图标

 .svg 文件放入 `@/icons/svg` 文件夹下之后就会自动导入。

**使用方式**

```js
<svg-icon icon-class="password" /> // icon-class 为 icon 的名字
```

菜单图标会自动引入`@/icons/svg`，放入此文件夹中图标就可以选择了

## 登录页开启注册用户功能

在菜单`参数设置`修改参数键名`sys.account.registerUser`设置`true`即可。默认为`false`关闭。

## 更换主题皮肤

1、项目主页-个人信息中选择切换主题

2、修改主框架页-默认皮肤，在菜单`参数设置`修改参数键名`sys.index.skinName`支持如下几种皮肤

- 蓝色 skin-blue
- 绿色 skin-green
- 紫色 skin-purple
- 红色 skin-red
- 黄色 skin-yellow

3、修改主框架页-侧边栏主题，在菜单`参数设置`修改参数键名`sys.index.sideTheme`支持如下几种主题

- 深色主题theme-dark
- 浅色主题theme-light

如需新增修改皮肤主题可以在`skins.css`中调整

顶部默认主题颜色在`skins.css`

```css
/** 蓝色主题 skin-blue **/
.navbar, .skin-blue .navbar {
	background-color: #3c8dbc
}
```

左侧默认主题颜色在`static\css\style.css`

```css
.navbar-static-side {
    background: #2f4050;
}

nav .logo {
    background-color: #367fa9;
}
```

## 横向菜单

默认的导航菜单都是在左侧，如果需要横向导航菜单可以做如下配置。

1、点击顶部最右侧个人中心头像，切换为横向菜单。（局部设置）

2、在参数管理设置`主框架页-菜单导航显示风格`，键值为`topnav`为顶部导航菜单。（全局设置）

## 如何去掉页脚及左侧菜单栏

1、去除页脚`修改style.css`，同时删除`index.html`元素

```css
#content-main {
    height: calc(100% - 91px);
    overflow: hidden;
}
```

```html
<div class="footer">
    <div class="pull-right">© [[${copyrightYear}]] RuoYi Copyright </div>
</div>
```

2、去左侧菜单栏（收起时隐藏左侧菜单）`修改style.css`

```css
body.fixed-sidebar.mini-navbar #page-wrapper {
    margin: 0 0 0 0px;
}

body.body-small.fixed-sidebar.mini-navbar #page-wrapper {
    margin: 0 0 0 0px;
}
```

3、去左侧菜单栏（收起时隐藏左侧菜单）`修改index.js`

```js
function() {
    if ($(this).width() < 769) {
        $('body').addClass('mini-navbar');
        $('.navbar-static-side').fadeIn(); // 换成 $('.navbar-static-side').hide();
        $(".sidebar-collapse .logo").addClass("hide");
    }
});

function SmoothlyMenu() {
    if (!$('body').hasClass('mini-navbar')) {
    	$(".navbar-static-side").show();  // 添加显示这一行
        $('#side-menu').hide();
        $(".sidebar-collapse .logo").removeClass("hide");
        setTimeout(function() {
            $('#side-menu').fadeIn(500);
        },
        100);
    } else if ($('body').hasClass('fixed-sidebar')) {
    	$(".navbar-static-side").hide();  // 添加隐藏这一行
        $('#side-menu').hide();
        $(".sidebar-collapse .logo").addClass("hide");
        setTimeout(function() {
            $('#side-menu').fadeIn(500);
        },
        300);
    } else {
        $('#side-menu').removeAttr('style');
    }
}
```

4、隐藏左侧菜单，需要添加`.canvas-menu`到body元素

```css
<body class = "canvas-menu"> 
```

## 左侧菜单如何点击不自动展开

在`index.js`把里面的`$('#side-menu').metisMenu();`

修改成如下方式，其中`toggle`属性表示是否自动展开

```js
$('#side-menu').metisMenu({
    toggle: false,
});
```

## 如何调整首页左侧菜单栏宽度

调整`style.css`对应样式宽度，例如宽度200修改成250

```css
body.fixed-sidebar .navbar-static-side, body.canvas-menu .navbar-static-side {
    width: 250px;
}
```

```css
nav .logo {
	width: 250px;
}
```

```css
#page-wrapper {
    margin: 0 0 0 250px;
}
```

## 如何默认显示表格卡片视图

在`options`中添加 `mobileResponsive` `cardView` 参数

```js
mobileResponsive: false,
cardView: true,
```

## 编辑和删除操作按钮不可用

这种情况一般是因为第一列不是唯一键或`formatter`序号造成的。解决方案如下，指定唯一列属性 配合删除/修改使用 未指定则使用表格行首列

在`options`中添加 `uniqueId`参数，`userId`修改成你表的唯一列字段。

```js
uniqueId: 'userId',
```

## 进入首页如何自动展开某菜单

例如，进入自动打开用户管理，调用`applyPath`，填入你请求菜单对应的url地址。

```js
applyPath("/system/role")
```

例如，进入系统自动跳转当前用户所拥有的第一菜单。

```js
var menus= [[${menus}]];
applyPath(menus[0].children[0].url);
```

## 进入首页如何默认记忆控制台

例如用户退出后，下次登陆系统，能默认打开之前工作路径。

可以在`index.html`，`index-topnav.html`，去掉`window.performance.navigation.type == 1`

```js
if($.common.equals("history", mode) && window.performance.navigation.type == 1)
```

换成

```js
if($.common.equals("history", mode))
```

## 首页侧边栏如何不自动收缩

1、`index.js`里面的`$('#side-menu').metisMenu();`，替换成如下：

```js
$('#side-menu').metisMenu({
    // 是否自动展开
    toggle: false,
});
```

2、去掉菜单联动`index.html`，`index-topnav.html`。

```js
// 是否页签与菜单联动
var isLinkage = false;
```

3、`index.js`里面的`menuItem`，`syncMenuTab`方法去掉下面三行代码。

```js
// $('.nav ul').removeClass("in");
// $dataObj.parents("ul").addClass("in")
// $dataObj.parents("li").addClass("active").siblings().removeClass("active").find('li').removeClass("active");
```

## 去除文件上传按钮

在一些特定情况不需要文件上传的小图标操作，可以把他们去掉。

这里`layoutTemplates`为上传控件模板，可以在这里重写上传控件中的元素样式

```js
$("#xxxx").fileinput({
    ....
	layoutTemplates: {
		actionDelete: '',
		actionUpload: '',
		actionZoom: '',
		indicator: ''
		.....
	},
	....
```

## 去除数据监控广告

服务监控中使用的`Driud`，默认底部有阿里的广告。如果是一个商业项目这个是很不雅也是不允许的

1. 找到本地maven库中的对应的druid-1.1.xx.jar文件，用压缩包软件打开
2. 找到support/http/resource/js/common.js, 打开找到 buildFooter 方法

```javascript
this.buildFooter();
buildFooter : function() {
	var html ='此处省略一些相关JS代码';
	$(document.body).append(html);
},
```

1. 删除此函数和及初始方法后覆盖文件
2. 重启项目后，广告就会消失了

## 翻页保留选择

1. 配置`checkbox`选项`field`属性为`state`

```javascript
{
	field: 'state',
	checkbox: true
},
```

1. 表格选项`options`添加`rememberSelected`

```javascript
rememberSelected: true,
```

## 汉化系统接口Swagger

1. 找到m2/repository/io/springfox/springfox-swagger-ui/x.x.x/springfox-swagger-ui-x.x.x.jar
2. 修改对应springfox-swagger-ui-x.x.x.jar包内`resources`目录下`swagger-ui.html`，添加如下JS代码

```html
<!-- 选择中文版 -->
<script src='webjars/springfox-swagger-ui/lang/translator.js' type='text/javascript'></script>
<script src='webjars/springfox-swagger-ui/lang/zh-cn.js' type='text/javascript'></script>
```

1. 本地修改结束后，在覆盖压缩包文件重启就实现汉化了

## **前端国际化流程**

1、html使用国际化#{资源文件key}

```html
<form id="signupForm">
	<h4 class="no-margins">登录：</h4>
	<p class="m-t-md">你若不离不弃，我必生死相依</p>
	<input type="text"     name="username" class="form-control uname"  th:placeholder="#{user.login.username}"   />
	<input type="password" name="password" class="form-control pword"  th:placeholder="#{user.login.password}"   />
	<div class="row m-t" th:if="${captchaEnabled==true}">
		<div class="col-xs-6">
			<input type="text" name="validateCode" class="form-control code" th:placeholder="#{user.login.code}" maxlength="5" autocomplete="off">
		</div>
		<div class="col-xs-6">
			<a href="javascript:void(0);" title="点击更换验证码">
				<img th:src="@{captcha/captchaImage(type=${captchaType})}" class="imgcode" width="85%"/>
			</a>
		</div>
	</div>
	<div class="checkbox-custom" th:classappend="${captchaEnabled==false} ? 'm-t'">
		<input type="checkbox" id="rememberme" name="rememberme"> <label for="rememberme" th:text="#{user.login.remember}">记住我</label>
	</div>
	<button class="btn btn-success btn-block" id="btnSubmit" data-loading="正在验证登录，请稍后..." th:text="#{user.login.submit}">登录</button>
</form>
```

2、js使用国际化 首先在文件引入`jquery-i18n-properties`依赖，然后在初始化后即可通过JS函数获取对应国际化文件的内容。

```javascript
<!--jQuery国际化插件-->
<script src="../static/js/jquery.i18n.properties.min.js" th:src="@{/js/jquery.i18n.properties.min.js}"></script>

<script th:inline="javascript">
	//获取应用路径
	var ROOT = [[${#servletContext.contextPath}]];

	//获取默认语言
	var LANG_COUNTRY = [[${#locale.language+'_'+#locale.country}]];

	//初始化i18n插件
	$.i18n.properties({
		path: ROOT + '/i18n/',//这里表示访问路径
		name: 'messages',//文件名开头
		language: LANG_COUNTRY,//文件名语言 例如en_US
		mode: 'map'//默认值
	});

	//初始化i18n函数
	function i18n(msgKey) {
		try {
			return $.i18n.prop(msgKey);
		} catch (e) {
			return msgKey;
		}
	}

	//获取国际化翻译值
	console.log(i18n('user.login.username'));
	console.log(i18n('user.login.password'));
	console.log(i18n('user.login.code'));
	console.log(i18n('user.login.remember'));
	console.log(i18n('user.login.submit'));
</script>
```

3、界面定义切换语言

```html
<a href="?lang=en_US"> 英语 </a>  
<a href="?lang=zh_CN"> 中文 </a>  
```

4、使用`html`使用模板引擎语法直接获取

```html
标签 <div th:text="#{user.login.username}"></div>
文本 <div>[[#{user.login.username}]]</div>
```

## 前端结构

```text
├── build                      // 构建相关  
├── bin                        // 执行脚本
├── public                     // 公共文件
│   ├── favicon.ico            // favicon图标
│   └── index.html             // html模板
│   └── robots.txt             // 反爬虫
├── src                        // 源代码
│   ├── api                    // 所有请求
│   ├── assets                 // 主题 字体等静态资源
│   ├── components             // 全局公用组件
│   ├── directive              // 全局指令
│   ├── layout                 // 布局
│   ├── plugins                // 通用方法
│   ├── router                 // 路由
│   ├── store                  // 全局 store管理
│   ├── utils                  // 全局公用方法
│   ├── views                  // view
│   ├── App.vue                // 入口页面
│   ├── main.js                // 入口 加载组件 初始化等
│   ├── permission.js          // 权限管理
│   └── settings.js            // 系统配置
├── .editorconfig              // 编码格式
├── .env.development           // 开发环境配置
├── .env.production            // 生产环境配置
├── .env.staging               // 测试环境配置
├── .eslintignore              // 忽略语法检查
├── .eslintrc.js               // eslint 配置项
├── .gitignore                 // git 忽略项
├── babel.config.js            // babel.config.js
├── package.json               // package.json
└── vue.config.js              // vue.config.js
```

