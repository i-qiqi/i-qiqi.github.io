---
title: "Linux"
date: 2019-05-17T20:21:10+08:00
draft: true
---
## Bash配置文件
- `/etc/profile` : 此文件为系统的每个用户设置环境信息,当**用户第一次登录**时,该文件被执行.并从/etc/profile.d目录的配置文件中搜集shell的设置./etc/profile中设定的变量(全局)的可以作用于任何用户
- `/etc/bashrc` : 为每一个运行bash shell的用户执行此文件.当**bash shell被打开**时,该文件被读取.
- `~/.bash_profile` : 每个用户都可使用该文件输入专用于自己使用的shell信息,当用户登录时,该文件仅仅执行一次!默认情况下,他设置一些环境变量,执行用户的.bashrc文件.
- `~/.bashrc` : 该文件包含专用于你的bash shell的bash信息,当**登录时以及每次打开新的shell**时,该该文件被读取.设定的变量(局部)只能继承/etc/profile中的变量,他们是"父子"关系.
- `~/.bash_login` :
- `~/.profile` :
- `~/.bash_logout`: 当**每次退出系统(退出bash shell)时**,执行该文件.

##  Reference
- <https://www.cnblogs.com/hellotracy/articles/5187350.html>
