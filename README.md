[myautocore 加强版预览信息OPENWRT专用](https://github.com/sirpdboy/myautocore)
======================
请 **认真阅读完毕** 本页面，本页面包含注意事项和如何使用。

## 功能说明：

###  来源LEAN大的  autocore 脚本。

###  本着人人为我，我为人人的原则，增加温度，类型，网卡MAC，时间等更多详细内容显示。不敢独享，特分享出来，为OPENWRT添砖加瓦。

<img src="doc/1.jpg" >
<img src="doc/2.jpg" >
## 编译使用方法 [![](https://img.shields.io/badge/-编译使用方法-F5F5F5.svg)](#编译使用方法-)


### 将myautocore添加至 LEDE/OpenWRT 源码的方法。

### 下载源码方法：

##由于习惯问题，会和LEAN大中的autocore冲突 ，建议编译前先删除：rm -rf package/lean/autocore

 ```Brach
 
    # 下载源码

    git clone https://github.com/sirpdboy/myautocore package/myautocore
	
    make menuconfig
	
 ``` 
 
### 配置菜单

 ```Brach
 
    make menuconfig
	
	# 找到 LuCI -> Applications, 选择 myautocore, 保存后退出。
	
 ``` 
### 编译

 ```Brach 
 
    # 编译固件
	
    make package/myautocore/compile V=s
 ```

## 说明 [![](https://img.shields.io/badge/-说明-F5F5F5.svg)](#说明-)

源码来源：https://github.com/sirpdboy/myautocore

============================

![screenshots](https://raw.githubusercontent.com/sirpdboy/openwrt/master/doc/说明2.jpg)

# My other project

<a href="#readme">
    <img src="https://img.shields.io/badge/-返回顶部-orange.svg" alt="图飞了😂" title="返回顶部" align="right"/>
</a>

