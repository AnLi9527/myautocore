[myautocore cpu和npu温度、频率、占用显示]
======================
请 **认真阅读完毕** 本页面，本页面包含注意事项和如何使用。

## 功能说明：

###  来源LEAN大的  autocore 脚本。

### 将myautocore添加至 OpenWRT 源码的方法。

### 下载源码方法：

##由于习惯问题，会和openwrt中的autocore冲突 ，建议编译前先删除原来的autocore!

 ```Brach
 
    # 下载源码

    git clone https://github.com/AnLi9527/myautocore package/myautocore
	
    make menuconfig
	
 ``` 
 
### 配置菜单

 ```Brach
 
    make menuconfig
	
	# 找到 Extra packages, 选择 myautocore, 保存后退出。
	
 ``` 
### 编译

 ```Brach 
 
    # 编译固件
	
    make package/myautocore/compile V=s
 ```

## 说明 

源码来源：https://github.com/sirpdboy/myautocore
