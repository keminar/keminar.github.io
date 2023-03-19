    记录我的成长

# 目录
    1. Linux
        1.1 ISO安装系统 
        1.2 硬盘安装系统
        1.3 常用软件安装
        1.4 虚拟机显卡直通
    2. Go 语言
        2.1 并行处理库
        2.2 http代理
    3. C 语言
        3.1 文件遍历小工具
        3.2 并行流式计算

## Linux

    1. 最近几年我都在使用Archlinux, ISO镜像可以在[官网]({% https://archlinux.org/download/ %})下载到,网易的源速度还不错.启动盘我是在Windows下制作的,我一般使用[AIO_Boot_Extractor]({% https://www.aioboot.com/en/download/ %})进行启动盘录制,初始化好U盘以后,只需要把ISO放进U盘目录即可系统安装. 当然也可以使用[其它工具]({% https://wiki.archlinux.org/title/USB_flash_installation_medium %}) . U盘引导成功后,对于目标系统要安装在DOS硬盘可以使用 [tiny.sh]({% /raw/linux-tools/master/arch/install-from-iso/tiny.sh %}), 如果要安装在GPT硬盘可以使用 [tiny_gpt.sh]({% /raw/linux-tools/master/arch/install-from-iso/tiny_gpt.sh %})

    2. 如果当前系统已经是Linux当然也可以不用制作启动U盘, 

可参考 [install-from-linux](/hub/linux-tools/tree/master/arch/install-from-linux) 完成系统安装

    3. 常用软件可以参考 [base](/hub/linux-tools/tree/master/arch/soft-base)  [desktop](/hub/linux-tools/tree/master/arch/soft-desktop)

    4. 虚拟机显卡直通可参考 [gpu-passthrough](/hub/linux-tools/tree/master/gpu-passthrough)

## Go 语言
    1. 语言内置的waitGroup 虽然可以实现并行处理,但是不够智能, 当一个任务处理完必须等待同批次的全处理完, 才会统一处理下一批任务, 我实现了一个优化版本 [go-parallel](/hub/go-parallel)

    2. [anyproxy](/hub/anyproxy) 是一个部署在Linux系统上的tcp流转发器，可以直接将本地或网络收到的请求发出，也可以将请求转到tunneld或SOCKS或charles等代理. [proxyUI](/hub/proxyui)为Anyproxy程序在Windows上使用提供可视化界面, 方便进行开发环境切换。

## C 语言
    1. 因为当目录文件很多时ls可能会卡死io,所以开发了[vls](/hub/vls)查看文件夹内文件时给一个的休息时间
    2. [broker](/hub/broker)通过linux系统管道将一个脚本的输出并发给多个脚本做输入
