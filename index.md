---
layout: page
title: Hello World!
tagline: Supporting tagline
---
{% include JB/setup %}

#安装完成第一页
##原理
jekyll 使用ruby开发，支持markdown、textile等语法。编写完成提交后，github将通过hook调用jekyll build来生成页面。

##安装

1. 安装ruby、gem
从[rubyinstaller.org](http://rubyinstaller.org/)分别[下载](http://rubyinstaller.org/downloads/) [Ruby 1.9.3-p484](http://dl.bintray.com/oneclick/rubyinstaller/rubyinstaller-1.9.3-p484.exe?direct)和[DevKit-tdm-32-4.5.2-20111229-1559-sfx.exe](https://github.com/downloads/oneclick/rubyinstaller/DevKit-tdm-32-4.5.2-20111229-1559-sfx.exe)，安装到指定目录（如C:\ruby193，C:\rubykit），并将它们（C:\Ruby193\bin;C:\Rubykit\bin）加入环境变量（PATH）。
2. 安装python
安装python主要为了支持高亮插件pygments，而插件需要通过python的easy_tool工具支持。搞起来相当麻烦，最后失败了，把`_config.yml`中的pygments设置成false不干了。
3. git支持
使用jekyll主要是为与github集成使用，把windows版的git客户端下载好解压。
4. jekyll
终于到了主角安装！！
> gem install jekyll
一句搞定

##使用
简单说两句

1. 发布博客
> rake post title="博客标题"
2. 发布自定义页面
> rake page name="path/pagename.html"

可增加目录
3. 启动服务
> jekyll server --watch
4. 生成页面
> jekyll build --watch

以上是jekyll的使用方式
---

与github的结合使用，从[jekyll-bootstrap](https://github.com/plusjade)clone一个库即可开始参照上述方法使用。基本命令如下：
{% highlight git %}

> git clone https://github.com/plusjade/jekyll-bootstrap.git lazyman.github.com

> cd lazyman.github.com

> git remote set-url origin git@github.com:lazyman/lazyman.github.com.git

> git push origin master

{% endhighlight %}

> rake post title="blog title"
> edit
> git commit
> git push github master

打开页面 `http://lazyman.github.io/`


还有个人信息需要相应的修改一下：

In `_config.yml` remember to specify your own data:
    
    title : My Blog =)
    
    author :
      name : Name Lastname
      email : blah@email.test
      github : username
      twitter : username
详细的操作方法参考[Jekyll Quick Start](http://jekyllbootstrap.com/usage/jekyll-quick-start.html)和[Jekyll Bootstrap](http://jekyllbootstrap.com)


## 帖子（博客）列表

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>

---

暂时先这样吧，本地浏览还有GBK编码问题
http://www.oschina.net/question/195686_72215
