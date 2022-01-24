# fixed-quizlet-to-anki-21-importer

不确定你家网络能不能成功下载，请先尝试原插件：

在anki内部插件窗口安装，输代码 538351043 ，重启，在上方“工具”栏里点 “Import From Quizlet” ，输入 quizlet 网站版上某个学习集（就是直接包含n个词语卡片的集合，不是folder）的网址。

网址例：https://quizlet.com/202478363/wordly-wise-3000-level-5-lesson-3-flash-cards/
（注意不是 folder 的网址！ folder 里面包含多个学习集）

然后点 Import 按钮，看看能不能成功。

如果你成功了，那很好！
如果报错显示 "Sorry, it's behind a captcha." ，那么你就看看我这个插件改版。

***

首先你必须有一个代理，俗称科学上网。它的作用相当于把你家网络对quizlet服务器的请求通过一个第三方代理服务器去转发。

开你的代理，用浏览器访问 quizlet.com ，看看会不会弹出一个 "Checking Your Browser" 或者让你做一个人机认证的界面。如果有，那就不太好办了，请换一个代理服务器。

如果没有，那没问题。打开系统设置看看你的代理端口是多少，记住这个“端口”值！！

![7TlNUe.png](https://s4.ax1x.com/2022/01/24/7TlNUe.png)

之后，把这个改版插件下载下来，把 xxx.ankiaddon 后缀名修改成 xxx.zip ，然后解压，打开，修改 _init_.py 里第89行的代码：

```
proxies = {'https': 'http://127.0.0.1:10809'}
```

把 10809 修改成 你自己代理的端口值，保存。然后把 _init_.py 、 config.json 、 manifest.json 三个文件打包到一个新zip里。注意不是把文件夹打包，是直接把三个文件打包！！！

这是官网对打包的介绍，很详细：

You can package up an add-on for distribution by zipping it up, and giving it a name ending in .ankiaddon.

The top level folder should not be included in the zip file. For example, if you have a module like the following:

```
addons21/myaddon/__init__.py
addons21/myaddon/my.data
```

Then the zip file contents should be:

```
__init__.py
my.data
```

If you include the folder name in the zip like the following, AnkiWeb will not accept the zip file:

```
myaddon/__init__.py
myaddon/my.data
```

把这个新 xxx.zip 改后缀名成 xxx.ankiaddon ，然后在anki里导入安装。之后应该就可以使用了，保持你的代理打开，重复本文开头介绍的操作。
