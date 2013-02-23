---
title       : 社会调查
subtitle    : social survey & research
author      : poemcao^Mail me:poemcao@gmail.com
job         : Department of Sociology & Psycholoy,Sichuan University
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
---

## 课程结构

### 前期工作

1. 社会调查概述

2. 课题
 
3. 调查设计
 
4. 抽样

5. 测量
 
6. 问卷设计
 


--- .class #id 
## 课程结构

### 调查过程

1. 资料收集

2. 资料处理

2.1 数据录入工具 EpiData
    [EpiData](http://www.epidata.dk/)协会于1999年在丹麦成立,采用Pascal开发。
    适用于：
    
    -Linux
    
    -Mac OS X
    
    -Windows
    

--- .class #id
## 课程结构
### 数据分析

1. 统计

2. 统计分析工具

2.1 SPSS

2.2 R  
  
  -[The R Project for Statistical Computing](http://www.r-project.org/)
  
  -[RStudio](http://www.rstudio.com/)

--- .class #id
## 课程结构
### 调查报告

--- .class #id
## 课程参考书目

1. 风笑天，现代社会调查方法，华中科技大学出版社，第四版

2. H.Russell Bernard,Research Method in Anthropology,Altamira press,2006

3. 周庭锐，市场调研：应用R软件，人民大学出版社，2012.10.

4. Robert I. Kabacoff，R语言实战(R in Action) (中译版：人民邮电出版社 2013.01.)



--- .class #id

## 社会调查分类

* 行政统计调查   
* 生活状况调查   
* 市场调查（市场调研）   
* 民意调查   
* 研究性调查


--- .class #id
## 抽样调查

基础统计知识：

抽样的思维模式：从总体中抽取*足够数量的*样本做为我们真实的观察对象，对想要观测的变量对样本对象进行测量，并用测量结果推论总体在变量上的情形。   
在抽样方法方面大致可以分为随机抽样和便利抽样，一般认为只有随机抽样才能取得具有代表性的样本，但是在实践过程中随机抽样很难实现，随机抽样需要满足三个基本条件：独立、互斥、抽中机会均等。


--- .class #id  
如果抽样框清晰完整，保证抽样机会均等是一件容易的事情：    
总体：从1-1000完整编号的1000人  
从中抽取：100人    


```r
sample(1000, 100)
```

```
##   [1] 562 723 558 796 484 726 481 559 801 741 144 441 635 108 232 688 221
##  [18] 449  86 507 816 351 732 781 432 362 434 683 292 305 749  23 208 135
##  [35] 330 773 762 518 357  41 506   7 971 150 454 638 641 960  39 275 704
##  [52] 871  59  67 703 968 403 218 992 515 513  68 882 370 185 667 934 511
##  [69] 865 361 845 668 260 224 868 436 229 521 670 380 721 837 168 290 583
##  [86] 783 222 687 190 753 696 974 308 589 921 852 599 800 797 269
```


R脚本执行的是不重复抽样，每个代码机会均等，不受抽到与否的影响。    

--- .class #id  

## 样本量的统计检定力(statistic power):
 考虑在某个可容忍的误差范围内，需要多大的样本数才能够满足样本对母体的代表性。在单纯的随机抽样且不重复抽取的前提下，公式如下：     

$$latex
 
n=\frac { { N }_{ { z }_{ a/2 }^{ 2 } }p(1-p) }{ { N }_{ { e }^{ 2 } }+{ z }_{ a/2 }^{ 2 }p(1-p) } 

$$

--- .class #id  
样本数量的设定：50万人中，LV包的拥有比例是0.04，我们愿意忍受0.01的抽样误差，通过R软件计算样本数量：  

```r
N = 5e+05

z = 1.96

p = 0.04

e = 0.01

n = (N * z^2 * p * (1 - p))/(N * e^2 + p * (1 - p))

n
```

```
## [1] 1474
```


--- .class #id





