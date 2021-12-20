---
layout: _post
title: java环境变量
date: 2020-04-04 19:46:43
tags: java
---
# linux配置java环境变量
### 一、打开
```bash
vi /etc/profile
```
<!-- more -->
### 二、加入↓↓↓
```bash
export JAVA_HOME=JDK路径，包括JDK文件夹
export JRE_HOME=/${JAVA_HOME}
export CLASSPATH=.:${JAVA_HOME}/libss:${JRE_HOME}/lib
export PATH=${JAVA_HOME}/bin:$PATH
```
#### 例如：
```bash
export JAVA_HOME=/java/jdk-14
export JRE_HOME=/${JAVA_HOME}
export CLASSPATH=.:${JAVA_HOME}/libss:${JRE_HOME}/lib
export PATH=${JAVA_HOME}/bin:$PATH
```

### 三、
```bash
source /etc/profile
```
