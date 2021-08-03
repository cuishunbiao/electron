#### 串口相关

使用**serialport**进行串口通信<br>

使用之前需安装 `npm install --global windows-build-tools` 这个插件 <br>

因为本机的node版本和electron对应的node版本不同，所以需要重新编译，使用electron-rebuild <br>

mac 执行 `./node_modules/.bin/electron-rebuild -v 10.1.1` 命令 <br>

windows 执行 `.\node_modules\.bin\electron-rebuild.cmd -v 10.1.1` 命令 有时需指定electron版本 <br>

如果上述命令失败，可参考 `https://www.cnblogs.com/baifangzi/p/12455879.html`

#### 打包注意事项

__安装包位数与node版本有关，64位node版本打包64位安装包，32位node版本打包32位安装包__

__所以打不同位数安装包时，建议代码拉到本地两份，一份64位node_modules，一份32位node_modules__

64位安装包先执行`npm run build`，再执行`npm run electron-build` <br>

32位安装包先执行`npm run build32`，再执行`npm run electron-build32` <br>


#### 以下几乎都是为了解决 serialport 相关的操作：  

electron-rebuild 根据当前 Electron 版本所使用的 Node.js 版本来重新编译项目。  

windows 下 electron-rebuild.md 命令报错。  

1、先是全局安装了 node-gyp ，命令 npm install -g node-gyp;  

2、又安装了 Python 2.7版本，配置环境变量;  

3、又安装了 安装Visual C ++构建环境(C++ 生成工具使用 Microsoft C++ 工具集、ATL 或 MFC 生成 Windows 桌面应用程序。)  

4、Rebuild Complete  

### 把相应的文件放到相应的目录

用户\AppData\Local\electron\Cache
目录nsis
网址:https://segmentfault.com/a/1190000018533945

