1.思路：借鉴之前有一篇blog，利用人人网数据进行新词挖掘的思想，做了改进优化；

2.原始思路： 利用jieba对文档分词，3个相邻词为一组，计算两个词的左信息熵，右信息熵，内部的凝聚度，并据此进行计算分数，根据分数大小获取新词；

3.优化点： 1.针对只能结合两个词，泛化到结合计算相邻N个词；

          2.内部互信息【凝聚度计算】，归一化到长度=1个词的情况下的值，可以实现不同长度词在同一纬度下进行比较；
          
          3.多进程处理，提高运行速度；
          
          4.添加过滤机制，根据停用词,高频常用词等进行过滤
          
4.入口文件： segment_multi.py   

  执行方式： python segment_multi.py
