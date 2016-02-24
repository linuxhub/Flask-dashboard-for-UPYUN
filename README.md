这是一个基于python flask框架开发的又拍云管理工具，提供了目录浏览、目录删除、文件查看、文件删除、创建目录、(多)文件上传等功能。


##安装相关库
```
pip install flask
```

##运行
```
python index.py
```
在浏览器中输入`http://127.0.0.1:5000`，回车进入。  

若需要自定义监听端口，请进入index.py，找到：
```python
if __name__ == '__main__':
    ## 调试模式
    app.run(debug=True)

    ##使用80端口，并允许其他主机使用
    #app.run(host='0.0.0.0', port=80)
```
根据需要修改即可。


##浏览器测试
* windows google chrome 34 => 正常
* windows firefox 27 =>正常
* windows internet explorer 8 =>无法愉快地使用
* linux firefox 27 =>正常
* linux google chrome 33 =>正常


##使用效果

###登录页面
![](./docs/login.png)

###成功登录后
![](./docs/after-login.png)

###进入其他目录
![](./docs/cd.png)

###查看文件内容
![](./docs/show-text.png)

###查看图片
![](./docs/show-img.png)

###创建目录
![](./docs/mkdir.png)

###上传文件
![](./docs/upload.png)

##文件限制
这个工具上传和查看文件的功能是先使上传或者下载到该工具中，然后与上传到又拍云或者显示给用户，所以不宜上传/下载大文件。当然本工具也对此做了限制（3mb）。

可以查看的文件格式限制为：'txt', 'py', 'c', 'cpp', 'java', 'html', 'htm','xml', 'png', 'jpg', 'jpeg', 'gif'。用户也可以在
```python
@app.route('/show', methods=['GET'])
def show():
    # ...
```
中自定义txt和img变量，以设定支持的文件。

##协议

MIT
