---
layout: post
title:  "在 OSX 中启动 MySQL"
date:   2015-07-30 17:12:24
categories: MySQL
---

### 1. 手动启动

{% highlight console %}

sudo /usr/local/mysql/support-files/mysql.server start

{% endhighlight %}

### 2. 自动启动

* 自己创建一个 launchd 脚本

{% highlight console %}
sudo vi /Library/LaunchDaemons/com.mysql.mysql.plist
{% endhighlight %}

* 主要内容是

{% highlight xml %}

<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plistversion="1.0">
    <dict>
        <key>KeepAlive</key>
        <true />
        <key>Label</key>
        <string>com.mysql.mysqld</string>
        <key>ProgramArguments</key>
        <array>
            <string>/usr/local/mysql/bin/mysqld_safe</string>
            <string>--user=mysql</string>
        </array>
    </dict>
</plist>

{% endhighlight %}

* 然后加载这个 launchd 脚本

{% highlight console %}

sudo chown root:wheel /Library/LaunchDaemons/com.mysql.mysql.plist 
sudo chmod 644 /Library/LaunchDaemons/com.mysql.mysql.plist 
sudo launchctl load -w /Library/LaunchDaemons/com.mysql.mysql.plist

{% endhighlight %}
