---
# try also 'default' to start simple
theme: Seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://tva1.sinaimg.cn/large/007c1Ltfgy1h0plytaly5j32yo1o0tj6.jpg
# apply any windi css classes to the current slide
class: "text-center"
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# persist drawings in exports and build
drawings:
  persist: true
# use UnoCSS (experimental)
css: unocss
---

### Welcome

---

<style>

* {
  
  font-family: HarmonyOS_Regular, -apple-system, "Noto Sans", "Helvetica Neue", Helvetica,
    "Nimbus Sans L", Arial, "Liberation Sans", "PingFang SC", "Hiragino Sans GB", "Noto Sans CJK SC",
    "Source Han Sans SC", "Source Han Sans CN", "Microsoft YaHei", "Wenquanyi Micro Hei",
    "WenQuanYi Zen Hei", "ST Heiti", SimHei, "WenQuanYi Zen Hei Sharp", sans-serif;
}

li:nth-of-type(1) {
  margin-top: 46px;
}
li {
  font-size: 24px;
  line-height: 100px !important;
}
</style>

# <a href="https://wiki.mbalib.com/wiki/%E8%B4%B9%E6%9B%BC%E5%AD%A6%E4%B9%A0%E6%B3%95" target="_blank">费曼学习法</a>

<img src="//tva4.sinaimg.cn/large/007c1Ltfgy1h5unv5hlm0j30mc0cmwh2.jpg" style="width: 700px;"/>

---

# 明确目标，了解概念用法

- 确立拆解目标，走出舒适区
- 学习成果可视化
- 学习过程不懂要重新回顾，简化语言

---

# 教学反馈，发现自己的能力边界

- 假装自己是位老师
- 使用简洁语言复述一遍所学知识
- 发现不足，重新回顾简化

---

# 感想

- 费曼学习法不仅是一种学习方法，更是一种简洁至上的思维方式
- 表面是在教别人，实际是以教代学，逼自己查漏补缺
- 及时的反馈能让你更有力的前行
- 此法能让记忆从无序走向有序，被动记忆走向主动理解并阐述

---

# <a href="https://baike.baidu.com/item/%E4%B8%89%E4%B8%8A%E4%B9%8B%E5%8A%9F/7917452" target="_blank">三上之功</a>

- 三上指枕上，马上，厕上
- 充分利用碎片化时间
- 平时可以三上空闲时间阅读一些小册，如<a href="https://wangdoc.com/javascript/" target="_blank"> JavaScript 教程</a>

---

# 互联网学习法

- 试想我想买一部耳机，发布帖子寻找建议
- 请问 200 块钱能买什么耳机
- 我觉得 200 块以下的耳机都是垃圾
- 上述两种询问方式哪种更能得到满意的答案呢？

---

# 类比学习法

- 节流与防抖
- 节流：每隔一段时间，只执行一次函数
- 防抖：在事件被触发 n 秒后才执行函数，如果这 n 秒内又被触发，则重新计时

---

# 防抖

<style>
  h1{
    margin-top: -20px;
  }
</style>

<div style="margin-top: 10px;">

```js {1-17|all}
function debounce(fn, delay) {
  // 定时器变量
  let timerId;
  return function (...args) {
    // 判断
    if (timerId) {
      // 清空定时器
      clearTimeout(timerId);
    }
    // 开启定时器执行函数
    timerId = setTimeout(() => {
      fn.apply(this, args);
      // 执行完成清空当前定时器,防止下次进来走到if逻辑
      timerId = null;
    }, delay);
  };
}

// 测试
<input type="text" />;
const input = document.querySelector("input");
const debounceTask = debounce((e) => {
  console.log(e.target.value);
}, 500);
input.addEventListener("input", debounceTask);
```

</div>

---

# 节流

```js {1-15|all}
function throttle(fn, delay) {
  // 定义开始时间
  let start = 0;
  return function (...args) {
    let now = Date.now();
    // 判断 当前时间 - 开始时间大于等于延迟时间
    if (now - start >= delay) {
      // 执行函数
      fn.apply(this, args);
      // 改变开始时间
      start = now;
    }
  };
}

// 测试
function task() {
  console.log("run task");
}
const throttleTask = throttle(task, 1000);
window.addEventListener("scroll", throttleTask);
```

---

# 类比学习法

- 用生活实践解释代码
- 防抖相当于英雄回城
- 节流相当于英雄的技能CD

---

# DDOS

<img src="//tvax4.sinaimg.cn/large/007c1Ltfgy1h5ux306b0tj31wm0rjb29.jpg" style="border-radius: 10px"/>

---

# 类比学习法

- 自己开一家饭馆和别人竞争
- 每天花钱雇佣 100 个老汉去其店里喝水，不消费
- 唯一的方式就是扩建（加服务器，加带宽，加工程师）

---

# 推演法

- 三段式逻辑推演
- JS 原型适用此法
- 不要使用生活的常识解释代码，保证a，b正确，c再扯都是正确的

---

# 例子

- 所有水果都是植物
- 香蕉是水果
- 香蕉是植物

---



# 例子

- <p style="margin-top: -10px;">所有函数都是 Function new出来的</p>
- <p style="margin-top: -10px;">Function 是一个函数</p>
- <p style="margin-top: -10px;">Function 是 Function new出来的</p>
<img src="//tvax3.sinaimg.cn/large/007c1Ltfgy1h5uxdxhvqzj30fy02l74v.jpg" style="border-radius: 10px; " />
<img src="//tva3.sinaimg.cn/large/007c1Ltfgy1h5uy791bvnj30jy02et9i.jpg" style="border-radius: 10px; margin-top: 10px"/>

---

# 例子

- <p style="margin-top: -10px;">所有函数都是 Function new出来的</p>
- <p style="margin-top: -10px;">Object是一个函数</p>
- <p style="margin-top: -10px;">Object 也是由 Function 构造出来的</p>

<img src="//tva2.sinaimg.cn/large/007c1Ltfgy1h5uygsbsldj30is05b0u4.jpg" style="border-radius: 10px; "/>


---


<img src="//tvax1.sinaimg.cn/large/007c1Ltfgy1h5uyx5papuj31180adwjt.jpg" style="border-radius: 10px; margin-bottom: 30px;"/>

```js {0|all}
console.log(Object.__proto__ === Function.prototype); // true
console.log(Function.__proto__ === Function.prototype); // true
console.log(Object.__proto__.__proto__ === Object.prototype); // true

console.log(Function instanceof Object); // true
console.log(Object instanceof Function); // true
console.log(Function instanceof Function); // true
console.log(Object instanceof Object); // true
```

--- 

# 构建知识体系树

- 学习需要大局观

---

<img src="//tva2.sinaimg.cn/mw690/007c1Ltfgy1h63y6twguej30pv0y3n2x.jpg" style="border-radius: 10px; height: 100%"/>