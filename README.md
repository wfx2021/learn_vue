# learn_vue

[视频教程](https://www.bilibili.com/video/BV1Zy4y1K7SH?p=4)

## 一、开发环境

1. 下载Vue.js
2. 安装Vue Devtools
3. 安装vscode插件：liveserver

## 二、helloworld

1. 必须有容器及对应的Vue实例

2. 容器与Vue为一对一关系，不可以多对一，一对多

3. 容器内容为html，被称为Vue模板

4. {{xxx}}内为js表达式，且xxx可以读取到data中的所有属性

5. Vue实例需要传入配置对象，如：el、data

6. Vue实例可以包含多个组件

    ```html
    <div id="demo">
    	<h1>Hello，{{name.toUpperCase()}}，{{address}}</h1>
    </div>
    
    <script type="text/javascript" >
    	Vue.config.productionTip = false //阻止 vue 在启动时生成生产提示。
    
        //创建Vue实例
        new Vue({
            el:'#demo', 	//el用于指定当前Vue实例为哪个容器服务，值通常为css选择器字符串。
            data:{ 			//data中用于存储数据，数据供el所指定的容器去使用，值我们暂时先写成一个对象。
                name:'atguigu',
                address:'北京'
            }
        })
    </script>
    ```
## 三、模板语法分类
1. 插值语法：**标签体**
   - 功能：解析标签体内容
   - 写法：{{xxx}}，xxx是js表达式，xxx可以直接读data中的属性
2. 指令语法：**标签属性**
   - 功能：解析标签（如：标签属性、标签体内容、绑定事件...）
   - 写法：如 v-bind:href="xxx" ，xxx是js表达式，同样可以直接读data中的属性
   - vue的指令都是v-???形式
   -  v-bind:href="xxx" 简写为 :href="xxx"

## 四、数据绑定

1. 单向绑定：vue中的data -> 页面（html），如：使用v-bind绑定的值
2. 双向绑定：vue中的data <-> 页面（html），如：使用v-model绑定，常用于绑定来获取用户操作，只能应用于表单输入类元素（有value值的），如input，单选框、select等
3. v-model:value="xxx"可以简写为v-model="xxx"

## 经验
1. 为避免data中属性名冲突，data中可以使用嵌套结构
   ```html
   <script type="text/javascript" >
    	Vue.config.productionTip = false 
   
        new Vue({
            el:'#demo', 	
            data:{
                user: {
                    name:'wfx'
                },			
                school: {
                    name:'atguigu',
                    address:'北京'
                }
            }
        })
    </script>
   ```

    

