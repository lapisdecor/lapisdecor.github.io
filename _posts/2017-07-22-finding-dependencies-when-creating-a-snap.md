---
layout: post
title:  "Finding dependencies when creating a Snap"
date:   2017-07-22 11:58:00
categories: snap
---
If you are making a python project for Ubuntu, you will soon want to make a snap of it. 
One of the main concerns you will have will be finding the dependencies for your project. Ubuntu Desktop comes with a lot of packages already installed and you usually install others while you are developing your open source project and you might not make notes of all the packages you had to install. Even if you do, the snap core comes with a very little subset of the packages installed in Ubuntu desktop. So you will have to start working as a dependencies detective.

So let's say you use this in your code:
{% highlight python %}
import subprocess

message = "Hello World!"
subprocess.Popen(['notify-send', message])

{% endhighlight %}

Here you are using the system notify-send command. You need to find out what package you need on your snap, so you can do:

{% highlight bash %}
dpkg -S notify-send
{% endhighlight %}

and you will find that the package you need is libnotify-bin (at least on my Ubuntu).

Another thing you can do is to install your snap and look in /snap/yoursnapname/current for signs of what is already there. That will give you a hint on what's missing when you compare it with your Ubuntu desktop system files. You can also list the installed packages in your system, you can do:

{% highlight bash %}
apt list --installed | grep packageyouwant

apt list --installed | grep libnotify-bin

{% endhighlight %}

Anyway, just remember, from now on, always make a list of your project dependencies, it will make the process of creating a snap a lot easier.
