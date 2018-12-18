FROM centos:latest 
MAINTAINER tidyko tidyko@qq.com 
#修改时区 
RUN rm -rf /etc/localtime && ln -s /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
#安装中文支持 
RUN yum -y install kde-l10n-Chinese && yum -y reinstall glibc-common
#配置显示中文 
RUN localedef -c -f UTF-8 -i zh_CN zh_CN.utf8
#设置环境变量 
ENV LC_ALL zh_CN.utf8 
#安装supervisor多进程管理工具，用于启动多进程
RUN yum -y install python-setuptools && easy_install pip && pip install supervisor
