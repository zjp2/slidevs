---
theme: seriph
background: https://source.unsplash.com/collection/94734566/1920x1080
class: text-center
highlighter: shiki
lineNumbers: false
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
drawings:
  persist: false
transition: slide-left
title: Welcome to Slidev
---

# 述职报告
述职人赵金鹏

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    下一页 <carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="abs-br m-6 flex gap-2">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon:edit />
  </button>
  <a href="https://github.com/slidevjs/slidev" target="_blank" alt="GitHub"
    class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---
transition: fade-out
---

# 工作回顾（2023年-1月 - 2023年3月）
<!-- 20231月-3月 -->
<img src="/public/gzhg.png" />
<!-- Slidev is a slides maker and presenter designed for developers, consist of the following features -->

<!-- - 📝 **Text-based** - focus on the content with Markdown, and then style them later
- 🎨 **Themable** - theme can be shared and used with npm packages
- 🧑‍💻 **Developer Friendly** - code highlighting, live coding with autocompletion
- 🤹 **Interactive** - embedding Vue components to enhance your expressions
- 🎥 **Recording** - built-in recording and camera view
- 📤 **Portable** - export into PDF, PNGs, or even a hostable SPA
- 🛠 **Hackable** - anything possible on a webpage -->

<br>
<br>

<!-- Read more about [Why Slidev?](https://sli.dev/guide/why) -->

<!--
You can have `style` tag in markdown to override the style for the current page.
Learn more: https://sli.dev/guide/syntax#embedded-styles
-->

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
Here is another comment.
-->

---
transition: fade-out
---

# 工作回顾(2023年3月 - 2023年6月)
<img src="/public/szbghsy.png" />

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---
transition: slide-up

level: 2
---

# 工作总结
  #### 1月到6月大多数时间都是以维护和旧的页面新功能为主(合同继承功能，收款计划什么的)，新增模块有：

  <img src="/public/skgl.png" height="390px" />

 
<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---
transition: slide-up

level: 2
---
<img src="/public/6405c0c4a46bed4dc1bd0742718ea1b.png"/> 

<style>
  img {
    width: 220px
  }
</style>

---

# bug统计
```text
仅统计的是禅道的不包含口头，或qq，或文档；不是我的问题过滤掉了。
```
<img src="/public/cdbug.png" />
<!-- <Bug /> -->

<style>
  img {
    height: 420px
  }
</style>

---
preload: false
---

# 能力提升
```text
  对整个开发结构更加了解了
  自己用node和mysql写的接口
```
<img src="/public/api.png" />

<style>
 h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}

img {
  height:400px
}
</style>

---

<img src="/public/mysql.png" />

```text
注册的时候加密，登录的时候解密 admin是手动加的 核心代码：
```
```js
  const sql = `select * from ev_users where username=?`
    db.query(sql, [userinfo.username], (err, results) => {
    // 执行失败sql
    if (err) {
      return res.cc(err)
    }

    console.log(results, 'results')
    // 用户名被占用
    if (results.length > 0) {
      return res.cc('用户名被占用，请更换其他用户名！')
    }

    // 使用bcrypt用户名可以使用 参数1密码，参数2加密生成的位数
    userinfo.password = bcrypt.hashSync(userinfo.password, 10)

    // 插入新用户
    const addUserSql = 'insert into ev_users set ?'

    const { username, password } = userinfo

    // 调用db。query执行sql遇见插入新用户
    db.query(addUserSql, { username, password }, (err, results) => {
      //sql执行失败
      if (err) return res.cc(err)

      // sql执行成功,影响行数不为1失败
      if (results.affectedRows !== 1) {
        return res.cc('注册用户失败，请稍后再试！')
      }

      // 注册成功
      res.cc('注册成功！', 200)
    })
  })
```
---

# 工具库
[code-tools-zjp](https://www.npmjs.com/package/code-tools-zjp)

```js
  /**
 * 排除对象某个键值
 * @param {*} obj 
 * @param {*} keyToExclude 
 * @returns 
 */
function excludeKey(obj, keyToExclude) {
  const newObj = {};
  for (const key in obj) {
    if (key !== keyToExclude) {
      newObj[key] = obj[key];
    }
  }
  return newObj;
}

```
---
  # 123
---
  # 总结收获

  ```text
    加深了对mysql的印象,会和后端对接起来更节约时间
    更熟悉node 可以用node做一些自己做demo的接口,让练习更贴合实际
  ```

---
---
 # 建议

  ```text
    随着系统不断的迭代，1.5，1.6应该会有更多的可配的东西；前后端有时间的时候最好能出一个文档，哪些字段是什么意思，这样实施人员就可以根据文档内容配置；
    因为很多时候，会被提给配置的东西，因为实施也不知道列表里面的字段代表啥意思
  ```
  
---
# END
