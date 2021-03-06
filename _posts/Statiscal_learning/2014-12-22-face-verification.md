---
layout: post
title: "人脸识别--汤晓欧教授2014-12-21发布会归来分享"
date: 2014-12-22 20:28:00
categories: Image
tags: machine_learning Image Face_verification
keywords: 统计 Statistical_learning
---

感谢强哥告知我这周日21号在南山3w咖啡厅有汤晓欧教授的人脸识别功能发布会， 趁着还没忘记当天的内容，把当天汤教授分享的内容以及其他信息与大家共享一下。 

这次会议是有 [科大迅飞][xunfei] 组织的人脸识别功能发布会，科大迅飞是一家专门从事语音智能开发的公司， 他提供一些语音交互功能的sdk接口给手机应用的开发商， 当天人数爆满，我问了周围的人，他们有些是因为之前用过他们公司的产品，所以过来看看他们开发了什么功能，迅飞希望在语音交互的基础上，再将人脸识别的功能加入， 因此，他们和汤教授实验室合作提供人脸识别的接口。除此之外这场发布会还邀请了其他一些交流者过来分享。背景大致介绍完了，是时候进入正题，也就是把重点放回汤教授他们研究室。

汤教授以他儿子的照片开头，讲述了他当年在开发自动为其儿子照片进行识别并且分类，从而引进到人脸识别的主题。 汤教授介绍了目前他们实验室主要有四个方面的研究:

* 人脸识别
* 物体识别
* 手势识别
* 群体检测

## 人脸识别

最近有接触图形识别这类的容易， 目前汤教授他们提供的人脸识别的接口也主要包括下面

* 人脸检测 

也就是在一张图片之后检测人脸所在的位置

* 人脸关键点检测

每张图片上人脸的位置都不一样， 因此需要确定一些关键点的位置，用于不同的脸进行比较。 一般我们看到的人脸关键点数目是5个， 分别是两个眼睛，鼻子和两边嘴角，汤教授他们可以提供5点，21点，68点，最高到194点的关键点检测

* 人脸识别

在汤教授他们的接口，人脸识别是给定两张图片之后，比较两张图片是否为同一个人。 他们号称全球最精准的人脸识别功能，既然说到全球最精准，那么一定需要有一个比较的机制，在人脸识别的领域，各大研究院就是使用 [LFW][LFW]图库作为比较, LFW将全球媒体出现的人物的脸部截取下来，进行算法比较，而比较的方式判断方式就是给定两张图片判断是否为同一个人，汤教授他们一开始基于高斯过程提出了Guassianface 的算法， 这算法的准确率首次超过了98.5%, 超过人类识别的准确率的97.5%, 相关的论文在下面链接 [Gaussianface][Gaussianface]
这里的人类识别能力其实是指只看到脸部五官的框架而去判断是否为一个人的准确率，如果给予全部图形，包括了身体和周围环境的信息之后，人类的准确率为99.2%. 因此并没有真正意义上的超越.

后来汤教授又基于deep learning 分别提出了 Deep ID (97.5%), Deep ID2(99.15%) 和 Deep ID2+(99.47%) 真正意义上面的超越人类识别的能力， 汤教授介绍了目前LFW国际前四名是他的这四个算法，第五名是Facebook的(97.35%)。 这是结果的 [链接][result], 相关的论文也可以到该链接可以获取.

中间汤教授介绍了一个很有趣的细节， 就是他们的训练资料是20万资料，这里并没有详细的介绍是20万个人还是20万张图片，他们在港中文邀请学生对于算法错误的人脸进行人为判断是否为同一个人，发现学生准确率大概为50%-60%，也就是跟猜的差不多。后面有路透社的记者去访问，也做了同样的测试，结果那个记者几乎都判断对了，原因主要有两个，第一，lfw集合上的人都是名人，这个记者几乎都看过他们的图片，了解他们，第二，她是外国人，因为lfw上面的图片大多数是外国人，他们对于外国人的识别比华人学生的识别能力强。 这里引起几个关键的思考， 机器学习是不是像人一样，看得足够多了之后就会有更好的分辨能力，这是汤教授提出的。另一个思考是站在我们自身的角度，如果我们是针对华人的识别，那么他的算法训练方式对于大多数为华人的图片有没有这么高的识别能力，这个是我们自己应用时需要注意的。

* 人脸属性

这个是他们未来开放的接口，可以根据人脸判断表情，年龄，性别等属性，这些属性的准确率几乎也都在90%以上。

# 物体识别

这也是图形识别的另一大范畴，也就是给定一张图片之后，能否识别出图片里面的物体，比如人，桌子，椅子等。 这个也有一个大家一起比较的数据集 [Imagenet][Imagenet], Imagenet 2014年提供200类的物体，在图片中识别出这个物体，2013年识别率最好的是 31%左右。 2014年参加比赛他们获得了第二名，准确率是40.66%, 第一名是google(43.93%)。 这是目前世界上最顶尖的研究所的准确率，也就是在物体识别这一块，机器学习似乎还有很长的路走。

# 手势识别

这个是他们目前正在研究的领域，通过识别手势，未来可以做很多事情。

# 人群检测

这个可以用于公共场所的维护.

# 其他介绍者与内容

这一部分介绍当天交流的其他介绍者以及他们介绍的内容，

* ibaby 全息智能管家

这个是介绍他们提供的24小时全息智能监控的家庭管家，可以24小时监控小孩的睡眠，未来还可以监控自身睡眠情况，给予适合的建议，想想都觉得可怕，谁要被监控啊。他们主页链接 [ibaby][ibaby]

* super ID 人脸登陆

super ID 是希望通过人脸登陆功能改变传统的密码登陆方式，这个是否可行有待商榷，不过应该有人会考虑说如果是放人像图片，那会不会有问题呢，汤教授介绍他们实验室已经实现活体检测，也就是前面一定是要一个活人才可以，即使拿出了娃娃这种东西也不行。

* Nao 机器人 

Nao 机器人是Aldebaran 公司提供的机器人，这机器人是可以自行开发程序的，演讲人的主要目的其实是希望听众从事机器人应用的开发，他们希望把这机器人当作苹果手机这样的载体，未来别人开发应用在他们的store。 

* google glassX

google glassX， 注意看到是google glassX, 他们相信未来是可穿戴设备的时代，他们要做的事情其实是做了google glass 的操作系统，到这边也是跟上面的机器人一样，希望大家基于他们的系统做开发应用。

[xunfei]: http://www.iflytek.com/
[LFW]: http://vis-www.cs.umass.edu/lfw/
[Gaussianface]: http://arxiv.org/pdf/1404.3840v2.pdf
[result]: http://vis-www.cs.umass.edu/lfw/results.html
[Imagenet]: http://www.image-net.org/
[ibaby]: http://www.ibabylabs.com.cn/

