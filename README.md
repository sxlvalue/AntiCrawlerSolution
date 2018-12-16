![AntiCrawlerSolution](https://github.com/AntiCrawlerSolution/AntiCrawlerSolution/blob/master/Static/%E7%88%AC%E8%99%AB.png)
# AntiCrawlerSolution(反爬解决方案)

1 . [写在开头](#1-写在开头)
- 1.1 [项目初衷](##1.1-项目初衷)
- 1.2 [项目介绍](##1.2-项目介绍)
- 1.3 [加入我们](##1.3-加入我们)
- 1.4 [感谢](##1.4-感谢)

2 . [反爬分类以及解决方案](#2-反爬分类以及对应解决方案)
- 2.1 [消息头鉴别](##2.1-消息头鉴别)
    - 2.1.1 [Referer鉴别](##2.1.1-Referer鉴别)
        - 2.1.1.1 [反爬原理](##2.1.1.1-反爬原理)
        - 2.1.1.2 [真实场景还原](##2.1.1.2-真实场景还原)
        - 2.1.1.3 [解决方案](##2.1.1.3-解决方案)
    - 2.1.2 [UserAgent鉴别](##2.1.2-UserAgent鉴别)
        - 2.1.2.1 [反爬原理](##2.1.2.1-反爬原理)
        - 2.1.2.2 [真实场景还原](##2.1.2.2-真实场景还原)
        - 2.1.2.3 [解决方案](##2.1.2.3-解决方案)
    - 2.1.3 [Cookie鉴别](##2.1.3-Cookie鉴别)
        - 2.1.3.1 [反爬原理](##2.1.3.1-反爬原理)
        - 2.1.3.2 [真实场景还原](##2.1.3.2-真实场景还原)
        - 2.1.3.3 [解决方案](##2.1.3.3-解决方案)
    - 2.1.4 [基于用户会话(Session)的反爬](##2.1.4-基于用户会话(Session)的反爬)
        - 2.1.4.1 [场景](##2.1.4.1-场景)
        - 2.1.4.2 [原理](##2.1.4.2-原理)
        - 2.1.4.3 [解决方案](##2.1.4.3-解决方案)
        
- 2.2 [IP判别](##2.2-IP判别)
    - 2.2.1 [相同IP鉴别](##2.2.1-相同IP鉴别)
        - 2.2.1.1 [反爬原理](##2.2.1.1-反爬原理)
        - 2.2.1.2 [真实场景还原](##2.2.1.2-真实场景还原)
        - 2.2.1.3 [解决方案](##2.2.1.3-解决方案)

- 2.3 [请求参数、主体判别](##2.3-请求参数、主体判别)
    - 2.3.1 [请求参数鉴别（参数保护）](##2.3.1-请求参数鉴别（参数保护）)
        - 2.3.1.1 [场景](##2.3.1.1-场景)
        - 2.3.1.2 [原理](##2.3.1.2-原理)
        - 2.3.1.3 [解决方案](##2.3.1.3-解决方案)
    - 2.3.2 [请求主体鉴别](##2.3.2-请求参数鉴别)
        - 2.3.2.1 [反爬原理](##2.3.2.1-反爬原理)
        - 2.3.2.2 [真实场景还原](##2.3.2.2-真实场景还原)
        - 2.3.2.3 [解决方案](##2.3.2.3-解决方案)

- 2.4 [验证码判定](##2.4-验证码判定)
    - 2.4.1 [图片验证码](##2.4.1-图片验证码)
        - 2.4.1.1 [反爬原理](##2.4.1.1-反爬原理)
        - 2.4.1.2 [真实场景还原](##2.4.1.2-真实场景还原)
        - 2.4.1.3 [解决方案](##2.4.1.3-解决方案)
    - 2.4.2 [语音验证码](##2.4.2-语音验证码)
        - 2.4.2.1 [反爬原理](##2.4.2.1-反爬原理)
        - 2.4.2.2 [真实场景还原](##2.4.2.2-真实场景还原)
        - 2.4.2.3 [解决方案](##2.4.2.3-解决方案)
    - 2.4.3 [极验验证码](##2.4.3-极验验证码)
        - 2.4.3.1 [反爬原理](##2.4.3.1-反爬原理)
        - 2.4.3.2 [真实场景还原](##2.4.3.2-真实场景还原)
        - 2.4.3.3 [解决方案](##2.4.3.3-解决方案)

- 2.5 [用户行为判别](##2.5-用户行为判别)
    - 2.5.1 [页面行为检测](##2.5.1-页面行为检测)
        - 2.5.1.1 [反爬原理](##2.5.1.1-反爬原理)
        - 2.5.1.2 [真实场景还原](##2.5.1.2-真实场景还原)
        - 2.5.1.3 [解决方案](##2.5.1.3-解决方案)
    - 2.5.2 [浏览器指纹检测](##2.5.1-页面行为检测)
        - 2.5.2.1 [反爬原理](##2.5.2.1-反爬原理)
        - 2.5.2.2 [真实场景还原](##2.5.2.2-真实场景还原)
        - 2.5.2.3 [解决方案](##2.5.2.3-解决方案)

- 2.6 [前端反调试Debug](##2.6-前端反调试Debug)
    - 2.6.1 [死循环Debug拦截DevTools](##2.6.1-死循环Debug拦截DevTools)
        - 2.6.1.1 [反爬原理](##2.6.1.1-反爬原理)
        - 2.6.1.2 [真实场景还原](##2.6.1.2-真实场景还原)
        - 2.6.1.3 [解决方案](##2.6.1.3-解决方案)
        
    - 2.6.2 [反无头浏览器（headless）](##2.6.2-反无头浏览器（headless）)
        - 2.6.2.1 [场景](##2.6.2.1-场景)
        - 2.6.2.2 [原理](##2.6.2.2-原理)
        - 2.6.2.3 [解决方案](##2.6.2.3-解决方案)

    - 2.6.3 [前端代码混淆](##2.6.2-前端代码混淆)
        - 2.6.3.1 [场景](##2.6.2.1-场景)
        - 2.6.3.2 [原理](##2.6.2.2-原理)
        - 2.6.3.3 [解决方案](##2.6.2.3-解决方案)


- 2.7 [APP验签](##2.7-APP验签)
    - 2.7.1 [代码混淆](##2.7.1-代码混淆)
        - 2.7.1.1 [反爬原理](##2.7.1.1-反爬原理)
        - 2.7.1.2 [真实场景还原](##2.7.1.2-真实场景还原)
        - 2.7.1.3 [解决方案](##2.7.1.3-解决方案)

- 2.8 [反无头浏览器（Headless）](##2.8-反无头浏览器（Headless）)


3 . [大V推荐](#3-大V推荐)

# 1 写在开头

## 1.1 项目初衷

    创建这个项目的初衷是有几点在日常工作和学习中的感悟：
        （1）接触到的反爬场景少，预先的知识储备不足，真正面对的时候学习周期长，解决难题时间长以致项目延期。
        
        （2）想要抽空学习，却不知道从哪里入手，没有合适的反爬的社群来交流讨论经验，没有完整可用的案例来辅助学习，
        网上的案例简单并且基础，不适合想要深入学习的人。
        （3）追求挑战性，这点我想是很多爬虫爱好者的“天性”，正如安全圈子一样，大家总用“英雄主义”的理想，想着没有攻克的难关。 
        所以，就需要新的“难关”抛出，于是，就希望建立这个项目以及相关小组能够帮助大家实现自己的“英雄梦”。
## 1.2 项目介绍

       项目其实很简单，我们会主要分为两个部分，也就是大家通常学习的顺序 - “理论”和“实战”，
       还有一些我们小组自研的开源库，帮助大家平常减少重复造轮子。
       
       理论方面： 我们会总结一下常见的反爬类型以及对应的解决方案、实际案例。
       
       实际案例方面：我们会结合真实的网站，详细的针对其反爬手段来进行分析。 

## 1.3 加入我们

    我们的想法很简单：“正如没有穿不透的墙，也没有反不了的反爬”
    加入我们，反“反爬”开源小组，可以直接加我微信：17610771895来加入我们。
    
## 1.4 感谢

    感谢`@cr`大佬的内容提交

# 2 反爬分类以及对应解决方案

## 2.1 消息头鉴别

### 2.1.1 Referer鉴别

#### 2.1.1.1 消息头鉴别

#### 2.1.1.2 真实场景还原

#### 2.1.1.3 解决方案

### 2.1.2 UserAgent鉴别

#### 2.1.2.1 消息头鉴别

#### 2.1.2.2 真实场景还原

#### 2.1.2.3 解决方案

### 2.1.3 Cookie鉴别

#### 2.1.3.1 消息头鉴别

#### 2.1.3.2 真实场景还原

#### 2.1.3.3 解决方案

### 2.1.4 基于用户会话(Session)的反爬

#### 2.1.4.1 场景
一般中小网站为了减轻数据库的压力，不会把请求次数记录在数据库中，因为每次请求都得update，对数据库压力相对较大，这类站点会选择把请求次数记录在会话数据中。
#### 2.1.4.2 原理
在用户session中记录请求频次，同时记录封禁次数，单次封禁时间可以跟封禁次数指数相关，以此限制单账户的请求频率。
#### 2.1.4.3 解决方案

这种方式的弱点在于，会话数据只对一次会话有效，通常用户访问web服务器时，服务器会颁发一个session_id，通过cookie发送给用户，用户只要触发封禁前清空cookie，重新建立会话就可以了。对于不需要登录的场景，还可以不带cookie（session_id）去请求服务器。

------

## 2.2 IP判别

### 2.2.1 相同IP鉴别

#### 2.2.1.1 消息头鉴别

#### 2.2.1.2 真实场景还原

#### 2.2.1.3 解决方案

------

## 2.3 请求参数、主体判别

### 2.3.1 请求参数鉴别（参数保护）

#### 2.3.1.1 场景

web的参数保护，主要用于表单防护，特别是注册和登录表单的防护，我们知道有效提供攻击成本的手段主要是基于IP的计数和基于用户的计数，其中基于用户的计数，攻击者会批量注册账号，因此注册和登录表单的保护变得尤其重要

#### 2.3.1.2 原理

参数保护主要依赖参数加密和混淆
参数加密主要是用JS加密表单需要提交的数据，后端解密这个数据。
加密方式很多，有单个参数加密的，也有所有参数整体加密的。
如果是单个参数加密的，不仅可以加密参数值，还可以加密参数名，还可以随机填充一些隐藏的input。
表单里的input数量随机，参数值随机，参数名也是随机的。然后利用JS控制DOM显示出真正有效的input。
这些JS代码通常会被保护起来。见[前端代码混淆](##2.6.2-前端代码混淆)

#### 2.3.1.3 解决方案

对于非动态的表单，可以逆向JS代码。
对于动态的表单，通常需要上headless浏览器

PS: 关于`headless`浏览器，现在主要推荐`google-chromium` 可以使用 `Remote debugging protocol`以及其相对应的高层封装[puppeteer](https://github.com/GoogleChrome/puppeteer)

### 2.3.2 请求主体鉴别

#### 2.3.2.1 消息头鉴别

#### 2.3.2.2 真实场景还原

#### 2.3.2.3 解决方案

------

## 2.4 验证码判定

### 2.4.1 图片验证码

#### 2.4.1.1 消息头鉴别

#### 2.4.1.2 真实场景还原

#### 2.4.1.3 解决方案

### 2.4.2 语音验证码

#### 2.4.2.1 消息头鉴别

#### 2.4.2.2 真实场景还原

#### 2.4.2.3 解决方案

### 2.4.3 极验验证码

#### 2.4.3.1 消息头鉴别

#### 2.4.3.2 真实场景还原

#### 2.4.3.3 解决方案

------

## 2.5 用户行为判别

### 2.5.1 页面行为检测

#### 2.5.1.1 消息头鉴别

#### 2.5.1.2 真实场景还原

#### 2.5.1.3 解决方案

### 2.5.2 浏览器指纹检测

#### 2.5.2.1 消息头鉴别

#### 2.5.2.2 真实场景还原

#### 2.5.2.3 解决方案

-----

## 2.6 前端防护

### 2.6.1 死循环Debug拦截DevTools

#### 2.6.1.1 消息头鉴别

#### 2.6.1.2 真实场景还原

#### 2.6.1.3 解决方案

### 2.6.2 反无头浏览器（Headless）

#### 2.6.2.1 场景

#### 2.6.2.2 原理

#### 2.6.2.3 解决方案

### 2.6.3 前端代码混淆

#### 2.6.3.1 场景

#### 2.6.3.2 原理

#### 2.6.3.3 解决方案

------

## 2.7 APP验签

### 2.7.1 代码混淆

#### 2.7.1.1 消息头鉴别

#### 2.7.1.2 真实场景还原

#### 2.7.1.3 解决方案

# 3 大V推荐

### 验证码相关： [冷月的博客](https://lengyue.me/)

### 脱壳破解相关：[吾爱破解](https://www.52pojie.cn/forum-5-1.html)

### 安全相关： [zzh](https://www.zzhsec.com)
