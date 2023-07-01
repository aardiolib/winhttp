# winhttp

WinHTTP 异步请求

## 安装
### npm

下载扩展库
``` bash
npm i @aardiolib/winhttp
```

复制扩展库到用户库
``` bash
robocopy .\node_modules\@aardiolib\ .\lib\ /E
```

## 示例

简单示例
```js
import win.ui;
import console;
import time.timer;
import winhttp;
import web.json;
/*DSG{{*/
winform = win.form(text="aardio form";right=636;bottom=379)
winform.add()
/*}}*/

console.open();
winform.show();

var getUrl = "http://eu.httpbin.org/get";
var postUrl = "http://eu.httpbin.org/post";

var http = winhttp();

http.config = {
	params = {
		a = 1;
		b = 2;
	}
	headers = {
		name = 2222;
		cookie = "id=1;token=2";
	}
	referer = "https://www.aardio.com/"
}

http.get(getUrl + "?c=3&b=4",{
	params = {
		e = 5;
	}
}).then(function(request){
	return request.json();
}).then(function(data){
	..console.dumpJson(data);
}).catch(function(err){
	..console.log("错误信息", err);
})

http.post(postUrl + "?c=3&b=4",..web.json.stringify({e = 5})).then(function(request){
	return request.json();
}).then(function(data){
	..console.dumpJson(data);
}).catch(function(err){
	..console.log("错误信息", err);
})

..console.log("请求已发送");
win.loopMessage();
```