# Python-34-
Python学习笔记(34)
# p124 以主程序方式运行
def add(a,b):
    return a+b

if__name__='__main__':
    print(add(10,20))  #只有当文件是主程序时才会执行运算

#此处另外开一个文件
import (输出上面模块的文件的文件名)
    print((上面模块的文件的文件名).add(100,200))  #只输出300，上面代码不输出



# p125 Python中的包
#Python程序中包含N多个包，每个包中包含N多个模块
#每个包中的模块都是独立的，有包这个概念能够很好的避免模块名称的冲突

#包当中包含一个__init__.py文件的目录称为包  目录里通常不包含__init__.py文件

#在demo8的模块中导入package1包
import package1.module_A 
print(package1.module_A.a)  #这个模块太长了可以取一个别名

import package1.module_A as ma  #ma是package1.module_A这个模块的别名
print(ma.a)

#在导入带有包的模块时，注意事项
import package1
import calc
#使用import方式进行导入，只能跟包或模块名

from package1 import module_A
from package1.module_A import a
#使用from...import可以导入包，模块，函数，变量



# p126 Python 中常用的内容模块
import sys
import time
import urllib.request  #点击urllib会自动跳入__init__.py文件中，urllib包中有一个request
import math
print(sys.getsizeof(24))
print(sys.getsizeof(45))
print(sys.getsizeof(True))
print(sys.getsizeof(False))

print(time.time())
print(time.localtime(time.time()))  #输出的是具体的年月日时分秒

print(urllib.request.urlopen('http://www.baidu.com').read())
#urllib用于读取来自网上(服务器)的数据标准库

print(math.pi)  #输出圆周率



# p127 第三方模块的安装与使用
#在终端中输入pip install模块名
pip install schedule
python
import schedule
import time

import schedule

def job():
    print('哈哈------')

schedule.every(3).seconds.do(job)
while True:
    schedule.run_pending()
    time.slep(1)



# p128 编码格式的介绍
#Python中的默认编码格式是UTF8，如果需要用其他的编码格式则在文件头部加上#encoding=gbk
