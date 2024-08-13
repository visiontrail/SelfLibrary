# 新员工必读材料

## 1. 配置开发电脑、虚拟机和各类权限
请参考：[各类权限,常用软件汇总](authority_software.md)

## 2. 学习NETCONF协议和CONFD使用
1. 入门认知：
    - [一篇华为编写的NETCONF入门介绍](http://172.21.6.174:4000/Commonwork/Reference/Netconf-huawei.pdf)
    - [CONFD官方出版的幻灯片](http://172.21.6.174:4000/Commonwork/Reference/netconfyangtutorial-140127071306-phpapp02.pdf)
    - [YANG语言中文](https://tonydeng.github.io/rfc7950-zh/)
    - [YANG语言原文](https://datatracker.ietf.org/doc/html/rfc7950)
2. 基础代码实战：
    - 172.21.27.166/oam_du/libxconfdexample （**云桌面内访问**）
3. 了解全部RPC报文内容
    - [H3C发布的Netconf报文说明](http://www.h3c.com/cn/d_201906/1208202_30005_0.htm)

## 3. 学习OAM系统基础需求和设计
- [NR-OAM总体设计说明](../A1-C0-oam_overview.md)
- [中移动南向接口规范(非实时更新，仅作学习用途)](http://172.21.6.174:4000/Attachment/cmcc-picocell-specification.pdf)


<br><br>

# 新员工入职项目（可选）
**请设计一个文件守护系统**，要求：
1. 当文件发生变化的时候，能够发送告警给对应的管理站
    - 可以自己在文件系统中创建的一个文件，并在进程启动时输入给该进程
    - 同时发送两种协议的告警（NETCONF、Restful），并使用任意你认为好用的方式验证。告警内容为文件名+文件大小+文件改变时间
2. 当文件发生变化的时候，提供文件上传功能
    - 提供用户可配置的上传地址
    - 自选协议（HTTP, FTP, sFTP etc...）
3. 当用户退出进程的时候，将对应的文件删除
4. 请集成已经提供好的日志系统
5. 完成后，请（**自愿**）发起一次组内评审+介绍（此项目为可选项，不影响最终评分）
6. 请使用C++实现，时间为2周