# PyProgrammer
# To make a Random List
As we all know the 973 project has been initiated. the memebers of scanning group includes:
- Yinshan Wang(Group Leader）
- Jinfeng Wu
- Quan Zhou
- Yiwen Zhang
- Zhengzheng Deng
- Bin Lu
- Jiaqi Gao

The purpose for me to write this scripts is to allocate each person randomly.For more information please see [LFCD](http://lfcd.psych.ac.cn/ "Title")

Firstly, Let's import some **basic modules!**

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
