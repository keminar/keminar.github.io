# 我的云窝

1. 本地构建测试安装

```
$ sudo pacman -S ruby
$ sudo gem install jekyll bundler
```

2. 把 `~/.local/share/gem/ruby/3.0.0/bin` 加到PATH环境变量

3. 如本目录没有 _Gemfile_  先创建文件 _Gemfile_ , 当前项目已经创建,内容如下
```
source 'https://rubygems.org'
gem 'github-pages', group: :jekyll_plugins
```

4. 安装
```
bundle install
bundle add webrick
```

5. 本地运行站点
```
$ bundle exec jekyll serve
```

6. 定期更新 `github-pages` gem 
```
bundle update github-pages
```
