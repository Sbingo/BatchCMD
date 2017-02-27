如果有很多Android app需要打包，或者不想每次输命令……

可以试试自定义个批处理，按照自己的需求完成打包工作。

打补丁也可以这么玩……

以下来自我写的bat文件

###效果
初始画面

![image](https://github.com/Sbingo/BatchCMD/raw/master/png/g1.png)

打包失败

![image](https://github.com/Sbingo/BatchCMD/raw/master/png/g2.png)

打包成功

![image](https://github.com/Sbingo/BatchCMD/raw/master/png/g3.png)

####命令：
@echo off

title XXX打包系统

color 0E

echo.

echo       ==================================

echo	   	   欢迎使用【XXX打包系统】

echo       ==================================

echo.

echo       1.正式包1号

echo.

echo       2.测试包1号

echo.

echo       3.正式包2号

echo.

echo       4.测试包2号

echo.

echo       Q.退出本系统

echo.

:input

set /p choice=请根据需求输入相应数字或字母，然后按回车

if "%choice%"=="1" goto 1

if "%choice%"=="2" goto 2

if "%choice%"=="3" goto 3

if "%choice%"=="4" goto 4

if /i "%choice%"=="Q" goto Q

echo 无效输入，请重新输入

echo.

goto input

:1

echo.

echo "请确保项目路径为【E:\Projects\1】，否则可能打包失败！"

echo.

cd E:\Projects\1

e:

del E:\Projects\1\app\build\outputs\apk\app-release.apk

del E:\Projects\1\app\build\outputs\apk\app-release-unaligned.apk

echo "完成删除旧包，按任意键将开始打包" & pause > nul

echo.

echo "3秒后开始"

ping -n 2 127.1>nul

echo "2秒后开始"

ping -n 2 127.1>nul

echo "1秒后开始"

ping -n 2 127.1>nul

echo "启动中，请稍候……"

color 6A

gradlew assembleRelease && (echo "打包成功，将打开文件所在目录,请使用文件【app-release.apk】，并确保这是刚打包好的文件，按任意键退出本系统" && start explorer "E:\Projects\1\app\build\outputs\apk" )|| echo "打包失败，按任意键退出本系统" & pause > nul

:2

echo.

echo "请确保项目路径为【E:\Projects\1】，否则可能打包失败！"

echo.

cd E:\Projects\1

e:

del E:\Projects\1\app\build\outputs\apk\app-debug.apk

del E:\Projects\1\app\build\outputs\apk\app-debug-unaligned.apk

echo "完成删除旧包，按任意键将开始打包" & pause > nul

echo.

echo "3秒后开始"

ping -n 2 127.1>nul

echo "2秒后开始"

ping -n 2 127.1>nul

echo "1秒后开始"

ping -n 2 127.1>nul

echo "启动中，请稍候……"

color 6A

gradlew assembleDebug && (echo "打包成功，将打开文件所在目录,请使用文件【app-debug.apk】，并确保这是刚打包好的文件，按任意键退出本系统" && start explorer "E:\Projects\1\app\build\outputs\apk" )|| echo "打包失败，按任意键退出本系统" & pause > nul

:3

echo.

echo "请确保项目路径为【E:\Projects\2】，否则可能打包失败！"

echo.

cd E:\Projects\2

e:

del E:\Projects\2\app\build\outputs\apk\app-release.apk

del E:\Projects\2\app\build\outputs\apk\app-release-unaligned.apk

echo "完成删除旧包，按任意键将开始打包" & pause > nul

echo.

echo "3秒后开始"

ping -n 2 127.1>nul

echo "2秒后开始"

ping -n 2 127.1>nul

echo "1秒后开始"

ping -n 2 127.1>nul

echo "启动中，请稍候……"

color 6A

gradlew assembleRelease && (echo "打包成功，将打开文件所在目录,请使用文件【app-release.apk】，并确保这是刚打包好的文件，按任意键退出本系统" && start explorer "E:\Projects\2\app\build\outputs\apk" )|| echo "打包失败，按任意键退出本系统" & pause > nul

:4
echo.

echo "请确保项目路径为【E:\Projects\2】，否则可能打包失败！"

echo.

cd E:\Projects\2

e:

del E:\Projects\2\app\build\outputs\apk\app-debug.apk

del E:\Projects\2\app\build\outputs\apk\app-debug-unaligned.apk

echo "完成删除旧包，按任意键将开始打包" & pause > nul

echo.

echo "3秒后开始"

ping -n 2 127.1>nul

echo "2秒后开始"

ping -n 2 127.1>nul

echo "1秒后开始"

ping -n 2 127.1>nul

echo "启动中，请稍候……"

color 6A

gradlew assembleDebug && (echo "打包成功，将打开文件所在目录,请使用文件【app-debug.apk】，并确保这是刚打包好的文件，按任意键退出本系统" && start explorer "E:\Projects\2\app\build\outputs\apk" )|| echo "打包失败，按任意键退出本系统" & pause > nul

:Q

exit
