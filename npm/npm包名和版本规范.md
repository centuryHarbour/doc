# 说明

> 对应在`package.json`里的字段是 `name`，对于 `npm` 包规范命名和版本号迭代有利于开发者使用和识别，更有利于作者维护。

## 包名基本规范，如下：

* **包名类似，拒绝发布**

  > 把包名中的标点符号去掉并与现有的包进行比较，相同则不允许发布

  例如：`react-native` 已经存在，那么诸如以下所示的包名是无法发布的：

  * reactnative
  * react_native
  * react_native
  
  *<font color=#fff566 size=3>Note:&nbsp;&nbsp;</font>* 8月5日后，`npm` 官方对于包的命名做了一些修改，主要是为了更好的防御「误植」攻击（8月5日长达两周的恶意攻击活动）

* **使用作用域**

  > 如果因为你起的包名与现有的包名太相近而被阻止发布这个包，那么找到一个独一无二包名最简单方法就是使用自己的作用域。你可以使用 `@ + 你的 npm 用户名` 加在包名前面将包划到你的 `npm` 账户作用域下。比如，我的 `npm` 用户名是 `favour` ，所以我的作用域是 `@favour` 。

  在 `package.json` 文件种把

  ```json
  {
    "name": "reactive-native"
  }
  ```

  修改成

  ```json
  {
    "name": "@/favour/reactive-native"
  }
  ```

* **包名不能只能使用小写，如：`jsonstream`**

  > 在npm注册表上，包名的历史是一个很小心的地添加条件限制的过程。在最早的时候，npm允许在包名上添加url安全字符，包括大写和小写字母。但是现在创建的包名中不能再有大写字母了，但是在npm注册表中那些包名中有大写字母的包依然存在也依然在使用，包名仅仅在大小写上的差异让我们第一次遇到了误植事件！可能大多数人遇到的例子是jsonstream。JSONStream 和 jsonstream 是不同的包但是很难区分，在一些大小写不敏感的系统中安装这些包就可能有问题

## 版本号基本规范，如下：

> 对应在`package.json`里的字段是 `version`，`npm` 有一套自己的版本控制标准—— `Semantic versioning`（语义化版本）

版本格式：主版本号.次版本.修订号，版本号递增规则如下：

* 主版本号：当你做了不兼容的API修改
* 次版本号：当你做了向下兼容的功能性新增
* 修订号：当你做了向下兼容的问题修正

*<font color=#fff566 size=3>Note:&nbsp;&nbsp;</font>* 通过 `npm version <update_type>` 自动改版版本， `update_type` 为 `patch` ， `minor` ， or `major` 其中之一，分别表示补丁，小改，大改。 

**参考网站：**

* [语义化版本号](https://semver.org/lang/zh-CN/)