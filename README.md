# vue3   [详细教程官网](https://cn.vuejs.org/guide/essentials/template-syntax.html)

### **Vue2 选项式 API vs Vue3 组合式API**   [笔记](https://github.com/biji-ziliao/vue3-biji/blob/master/01-Vue3%E5%85%A5%E9%97%A8/Vue3%E5%85%A5%E9%97%A8.md#1-vue2-%E9%80%89%E9%A1%B9%E5%BC%8F-api-vs-vue3-%E7%BB%84%E5%90%88%E5%BC%8Fapi)

### **组合式API - setup选项**   [笔记](https://github.com/biji-ziliao/vue3-biji/blob/master/01-Vue3%E5%85%A5%E9%97%A8/Vue3%E5%85%A5%E9%97%A8.md#%E7%BB%84%E5%90%88%E5%BC%8Fapi---setup%E9%80%89%E9%A1%B9)

### **setup中写代码的特点**   [代码](https://github.com/biji-ziliao/vue3-biji/blob/master/01-Vue3%E5%85%A5%E9%97%A8/vue3-demo/src/01-setup.vue)     [笔记](https://github.com/biji-ziliao/vue3-biji/blob/master/01-Vue3%E5%85%A5%E9%97%A8/Vue3%E5%85%A5%E9%97%A8.md#2-setup%E4%B8%AD%E5%86%99%E4%BB%A3%E7%A0%81%E7%9A%84%E7%89%B9%E7%82%B9)

### **组合式API - reactive和ref函数**   [笔记](https://github.com/biji-ziliao/vue3-biji/blob/master/01-Vue3%E5%85%A5%E9%97%A8/Vue3%E5%85%A5%E9%97%A8.md#%E7%BB%84%E5%90%88%E5%BC%8Fapi---reactive%E5%92%8Cref%E5%87%BD%E6%95%B0)

**reactive 对比 ref :**

1. 都是用来生成响应式数据
2. 不同点
    1. reactive不能处理简单类型的数据
    2. ref参数类型支持更好，但是必须通过.value做访问修改
    3. ref函数内部的实现依赖于reactive函数
3. 在实际工作中的推荐
    1. 推荐使用ref函数，减少记忆负担，小兔鲜项目都使用ref

### **组合式API - computed**   [代码](https://github.com/biji-ziliao/vue3-biji/blob/master/01-Vue3%E5%85%A5%E9%97%A8/vue3-demo/src/03-computed.vue)     [笔记](https://github.com/biji-ziliao/vue3-biji/blob/master/01-Vue3%E5%85%A5%E9%97%A8/Vue3%E5%85%A5%E9%97%A8.md#%E7%BB%84%E5%90%88%E5%BC%8Fapi---computed)

计算属性基本思想和Vue2保持一致，组合式API下的计算属性只是修改了API写法

### **组合式API - watch**   [代码](https://github.com/biji-ziliao/vue3-biji/blob/master/01-Vue3%E5%85%A5%E9%97%A8/vue3-demo/src/04-watch.vue)     [笔记](https://github.com/biji-ziliao/vue3-biji/blob/master/01-Vue3%E5%85%A5%E9%97%A8/Vue3%E5%85%A5%E9%97%A8.md#%E7%BB%84%E5%90%88%E5%BC%8Fapi---watch)

侦听一个或者多个数据的变化，数据变化时执行回调函数，俩个额外参数 immediate控制立刻执行，deep开启深度侦听

### **组合式API - 生命周期函数**   [代码](https://github.com/biji-ziliao/vue3-biji/blob/master/01-Vue3%E5%85%A5%E9%97%A8/vue3-demo/src/05-%E7%94%9F%E5%91%BD%E5%91%A8%E6%9C%9F%E5%87%BD%E6%95%B0.vue)     [笔记](https://github.com/biji-ziliao/vue3-biji/blob/master/01-Vue3%E5%85%A5%E9%97%A8/Vue3%E5%85%A5%E9%97%A8.md#%E7%BB%84%E5%90%88%E5%BC%8Fapi---%E7%94%9F%E5%91%BD%E5%91%A8%E6%9C%9F%E5%87%BD%E6%95%B0)

### **组合式API - 父子通信**   [代码](https://github.com/biji-ziliao/vue3-biji/tree/master/01-Vue3%E5%85%A5%E9%97%A8/vue3-demo/src)     [笔记](https://github.com/biji-ziliao/vue3-biji/blob/master/01-Vue3%E5%85%A5%E9%97%A8/Vue3%E5%85%A5%E9%97%A8.md#%E7%BB%84%E5%90%88%E5%BC%8Fapi---%E7%88%B6%E5%AD%90%E9%80%9A%E4%BF%A1)

### **组合式API - 模版引用**   [代码](https://github.com/biji-ziliao/vue3-biji/blob/master/01-Vue3%E5%85%A5%E9%97%A8/vue3-demo/src/08-%E6%A8%A1%E6%9D%BF%E5%BC%95%E7%94%A8.vue)     [笔记](https://github.com/biji-ziliao/vue3-biji/blob/master/01-Vue3%E5%85%A5%E9%97%A8/Vue3%E5%85%A5%E9%97%A8.md#%E7%BB%84%E5%90%88%E5%BC%8Fapi---%E6%A8%A1%E7%89%88%E5%BC%95%E7%94%A8)

> 概念：通过 ref标识 获取真实的 dom对象或者组件实例对象
> 

**1. 基本使用**

> 实现步骤：
> 
> 1. 通过ref标识绑定ref对象到标签
> 2. 调用ref函数生成一个ref对象

**2. defineExpose**

> 默认情况下在 <script setup>语法糖下组件内部的属性和方法是不开放给父组件访问的，可以通过defineExpose编译宏指定哪些属性和方法容许访问 说明：指定testMessage属性可以被访问到
> 

### **组合式API - provide和inject**   [代码](https://github.com/biji-ziliao/vue3-biji/blob/master/01-Vue3%E5%85%A5%E9%97%A8/vue3-demo/src/09-provide%E5%92%8Cinject.vue)     [笔记](https://github.com/biji-ziliao/vue3-biji/blob/master/01-Vue3%E5%85%A5%E9%97%A8/Vue3%E5%85%A5%E9%97%A8.md#%E7%BB%84%E5%90%88%E5%BC%8Fapi---provide%E5%92%8Cinject)

**1. 作用和场景**

> 顶层组件向任意的底层组件传递数据和方法，实现跨层组件通信
> 

**2. 跨层传递普通数据**

> 实现步骤
> 
> 1. 顶层组件通过 `provide` 函数提供数据
> 2. 底层组件通过 `inject` 函数提供数据

**3. 跨层传递响应式数据**

> 在调用provide函数时，第二个参数设置为ref对象
> 

**4. 跨层传递方法**

> 顶层组件可以向底层组件传递方法，底层组件调用方法修改顶层组件的数据
> 

### **状态管理 - Pinia**   [代码](https://github.com/biji-ziliao/vue3-biji/tree/master/02-Pinia/pinia%26%E5%A4%A7%E4%BA%8B%E4%BB%B6%E7%AE%A1%E7%90%86%E7%B3%BB%E7%BB%9F/vue3-pinia-demo)     [笔记](https://github.com/biji-ziliao/vue3-biji/blob/master/02-Pinia/Pinia.md#vue3-%E7%8A%B6%E6%80%81%E7%AE%A1%E7%90%86---pinia)

### **后台数据管理系统**

**Pinia - 构建用户仓库 和 持久化**

**Pinia - 配置仓库统一管理**

**数据交互 - 请求工具设计**

**登录注册页面 [element-plus 表单 & 表单校验]**
