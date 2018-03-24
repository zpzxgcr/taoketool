# taoketool
KK券 tool
编译方式   用 prebuild -t 1.8.4 -r electron  指定你要编译的包 注意必须是nan的写法开发插件
然后把编译出来的build的文件复制到你的项目目录下去 在拷贝过来的目录下面  输入 npm rebuild --runtime=electron --target=1.8.4 --disturl=atom.io/download/atom-shell --build-from-source 重新编译一下electron 可以用的包 就能直接使用

loadAllWindow()
	获取所有的窗口句柄（QQ & 微信）
	使用：obj.loadAllWindow()
	返回值：json串，
	例如：
	{"QQ":
	     {123456:"窗口标题",...},
	  "Wechat":{147258:"窗口标题", 234689:"窗口2", ...}
	}


sendMsgToWindow(句柄, flag)
	参数：
		句柄：loadAllWindow函数返回的句柄，
		flag：1：回车发送消息；2：ctrl+回车发送消息
	返回值：json串，{"status":1, "msg":"发送成功"} 或 {"status":0, "msg":"发送失败"}