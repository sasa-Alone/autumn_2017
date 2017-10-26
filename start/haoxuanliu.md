# 尝试较正式的使用Markdown
* 虽然可能不太好看
***
## 乱七八糟的练习
下面是比较全的操作:
[我在简书上的操作](http://www.jianshu.com/p/a96b77ba86e5)
***
引入图片在简书比较方便，直接拖，而且不用图床什么的，比较方便

**刺客信条（粗体）**
[]()
![刺客信条](http://upload-images.jianshu.io/upload_images/8685793-f63e8581c27758f4.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

* 多行代码的操作还不错
## KNN实现
1.算当前点与所有点的距离，排序
2.找前k个点查看分类
3.点最多的分类==当前点的分类
4.暂无k-means
```
from numpy import *
import operator

def createDataSet():
    group = array([[1.0,1.1],[1.0,1.0],[0,0],[0,0.1]])
    labels = ['A','A','B','B']
    return group, labels

def classify0(inX, dataSet, labels, k):
    dataSetSize = dataSet.shape[0]
    diffMat = tile(inX, (dataSetSize,1)) - dataSet
    sqDiffMat = diffMat**2
    sqDistances = sqDiffMat.sum(axis=1)
    distances = sqDistances** 0.5
    sortedDistIndicies = distances.argsort()
    classCount={}    
    for i in range(k):
        voteIlabel = labels[sortedDistIndicies[i]]
        classCount[voteIlabel]=classCount.get(voteIlabel,0)+1
    sortedClassCount = sorted(classCount.iteritems(),key=operator.itemgetter(1),reverse=True)
    return sortedClassCount[0][0]

```

感觉完成的还可以哈，不知道交作业会不会有格式问题
klsdjft
