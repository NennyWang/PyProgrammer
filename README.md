# PyProgrammer
# To make a Random List
众所周知973项目已经正式开始了，扫描组的组员包括以下人员:
- Yinshan Wang(Group Leader）
- Jinfeng Wu
- Quan Zhou
- Yiwen Zhang
- Zhengzheng Deng
- Bin Lu
- Jiaqi Gao

写这段代码的目的是为了练习如何分配组员，我们课题组的网站为 [LFCD](http://lfcd.psych.ac.cn/ "Title")

首先我们先导入Python的**基本模块** 

```python

import time,random,math
import numpy as np
import pandas as pd
from matplotlib import pyplot as plt

staff_names = ['Yinshan','Jinfeng','Quan','Yiwen','Zheng','Bin','Jiaqi']  #主试姓名
duty_dates = np.zeros((31,7))                                             #生成一个行为日期，列为主试的array
date_range = pd.date_range('8/1/2016','8/31/2016')                        #值班日期8月1日-30日
Schedule = pd.DataFrame(duty_dates,columns=staff_names,index=date_range)   #生成31天*7人的DataFrame
Weekdays = [i+1 for i in range(7)]                                         #一个用1-7代表周一至周日的list
Weekdays_Aug = [Weekdays[i%7] for i in range(31)]                          #每月对应周几
Schedule['Weekdays']=Weekdays_Aug                                          #加入到dataframe中
Schedule=Schedule[Schedule['Weekdays']<=5]                                 #筛选出工作日
```
