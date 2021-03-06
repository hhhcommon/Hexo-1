---
title: Spark累加器的使用方法
date: 2018-03-17 17:40:09
tags: Spark
categories: 大数据
---
运行spark程序，使用到了累加器Accumulator，目前使用的是spark2.3.0，累加器Accumulator的定义方法变了，具体查看详细内容。
<!-- more -->
之前spark1.6.0时，累加器的定义及使用方式为：
```
Accumulator<Integer> accum = sc.accumulator(0);
sc.parallelize(Arrays.asList(1, 2, 3, 4)).foreach(x -> accum.add(x));
// ...
// 10/09/29 18:41:08 INFO SparkContext: Tasks finished in 0.317106 s
accum.value();
// returns 10
```
在spark2.3.0中，累加器的定义方式应该为：
```
LongAccumulator accum = jsc.sc().longAccumulator();
sc.parallelize(Arrays.asList(1, 2, 3, 4)).foreach(x -> accum.add(x));
// ...
// 10/09/29 18:41:08 INFO SparkContext: Tasks finished in 0.317106 s
accum.value();
// returns 10
```
之前的方式已被标记为Deprecated。
也可以如此，先定义，在注册到SparkConf：
```
LongAccumulator countDftResult = new LongAccumulator();
LongAccumulator countFailed = new LongAccumulator();
sc.register(countDftResult); // 注册累加器
sc.register(countFailed);
```
如果不注册，会出现Accumulator must be registered before send to executor异常。
到这里就基本可以使用累加器了，谢谢大家，如果有什么问题，请留言。