## vuejs学习札记

1. 响应式开发

   可以在运行的时候，直接从控制台进行数据的交互。

   ![image-20210525222225506](C:\Users\Phyll\AppData\Roaming\Typora\typora-user-images\image-20210525222225506.png)

2. vuejs的for循环   在指令中使用 v-for ,其中，item就是对movies数值的遍历

   ```
    <li v-for="item in movies">{{item}}</li>
   ```

   

3 vuejs实现计数器, 直接用v-on：click 命令也是可以的，但是还有更加完善的方法

```
<body>
    <div id="app">
        {{message}}
        {{counter}}
        <button v-on:click="counter++">+</button>
        <button v-on:click="counter--">-</button>
    </div>
    <script>
        const app = new Vue({
            el: "#app",
            data:{
                message:"今天要实现计数器",
                counter:0
            }
        })
    </script>
    <script src="vue.js"></script>
</body>
```

我们在method方法来实现

```
<body>
    <div id="app">
        {{message}}
        {{counter}}
        <!-- 第二种方法，使用函数 ,在后面会直接绑定上方法名-->
        <button v-on:click="add">+</button>
        <button v-on:click="sub">-</button>
    </div>
    <script>
        const app = new Vue({
            el: "#app",
            data:{
                message:"今天要实现计数器",
                counter:0
            },
            methods:{
                add: function(){
                    this.counter++
                    //这里地方要用this来指代是这个对象里面的counter，不然就会出现局部变量和全局变量的问题
               
                },
                sub: function(){
                    this.counter--
                }

            }
        })
    </script>

</body>
```



