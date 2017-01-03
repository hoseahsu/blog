# 使用jekyll搭建个人博客

------

1. [ruby 安装](#ruby-install)


<a name="ruby-install"></a>
# 0X00 快速正确的安装 Ruby, Rails 运行环境

## 0X01 － 安装 RVM

RVM 是干什么的这里就不解释了，后面你将会慢慢搞明白。

```bash
$ gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3
$ curl -sSL https://get.rvm.io | bash -s stable
# 如果上面的连接失败，可以尝试: 
$ curl -L https://raw.githubusercontent.com/wayneeseguin/rvm/master/binscripts/rvm-installer | bash -s stable
```

然后，载入 RVM 环境（新开 Termal 就不用这么做了，会自动重新载入的）

```bash
$ source ~/.rvm/scripts/rvm
```

修改 RVM 下载 Ruby 的源，到 Ruby China 的镜像:
```bash
echo "ruby_url=https://cache.ruby-china.org/pub/ruby" > ~/.rvm/user/db
```

检查一下是否安装正确

```bash
$ rvm -v
rvm 1.22.17 (stable) by Wayne E. Seguin <wayneeseguin@gmail.com>, Michal Papis <mpapis@gmail.com> [https://rvm.io/]
```

## 0X02 － 用 RVM 安装 Ruby 环境

可以先上[这里](https://www.ruby-lang.org/zh_cn/downloads/)查看一下最新的稳定版（**https://www.ruby-lang.org/zh_cn/downloads/**）

```bash
$ rvm requirements
$ rvm install 2.3.1
```
同样继续等待漫长的下载，编译过程，完成以后，Ruby, Ruby Gems 就安装好了。

## 0X03 － 设置 Ruby 版本

RVM 装好以后，需要执行下面的命令将指定版本的 Ruby 设置为系统默认版本

```bash
$ rvm use 2.3.1 --default
```

同样，也可以用其他版本号，前提是你有用 rvm install 安装过那个版本

这个时候你可以测试是否正确

```bash
$ ruby -v
ruby 2.3.1 ...

$ gem -v
2.3.4

$ gem sources --add https://gems.ruby-china.org/ --remove https://rubygems.org/
```

安装 Bundler

```bash
$ gem install bundler
```

## 0X04 － 使用 Ruby China 镜像

RubyGems 一直以来在国内都非常难访问到，在本地你或许可以翻墙，当你要发布上线的时候，你就很难搞了！

这是一个完整 RubyGems 镜像，你可以用此代替官方版本，我们是基于国内 CDN + 国外服务器的方式，能确保几乎无延迟的同步。

```bash
$ gem update --system # 这里请翻墙一下
$ gem -v
2.6.7

$ gem sources --add https://gems.ruby-china.org/ --remove https://rubygems.org/
$ gem sources -l
https://gems.ruby-china.org
# 确保只有 gems.ruby-china.org
```

## 0X05 － 安装 Rails 环境

上面 3 个步骤过后，Ruby 环境就安装好了，接下来安装 Rails

```bash
$ gem install rails
```
然后测试安装是否正确

```bash
$ rails -v
Rails 5.0.0.1
```
然后开始你的 Ruby，Rails 之旅吧。
欢迎来到 Ruby 的世界！

# 0X10 安装jekyll

```bash
$ gem install jekyll
```

# 0X20 创建一个jekyll博客

```bash
$ jekyll new myblog
$ cd myblog
```

```bash

```



# 参考链接

1. [如何快速正确的安装 Ruby, Rails 运行环境](https://ruby-china.org/wiki/install_ruby_guide)

2. [RubyGems 镜像- Ruby China](http://gems.ruby-china.org/)
