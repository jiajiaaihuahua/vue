## javascript 实现双向数据绑定(原，转载请注明出处)
* javascript 如何实现双向数据绑定呢，我的理解是，数据的值改变，所有涉及到该数据的计算，状态等相关操作都会改变，这是一向，其次如果涉及此数据的例如input修改了此值，那么这个值也会被相应的修改。(此话是我的理解，纯属天马行空，看不懂正常。)<br/>&nbsp;&nbsp;&nbsp;&nbsp;我们知道在Vue.js中可以实现这种数据绑定（MVVM模式），也实现了当数据发生改变时可以做一些操作的功能，那JavaScript该如何实现呢，且看我一一道来。
#### 第一步,也是最后一步，也是最关键的一步。重写变量的set方法，当变量被设置值的时候，必调用他的set方法。
```html
<html>
<head>
</head>
	<body>
        <input type='text' id = 'model'/>
        <script>
            // 另外一种定义变量的方法哟
            var model = new Object(null);
            Object.defineProperty(model, 'results',{
                set:function(value){
                    results = value;
                    // 每当修改了model.results的值，就会触发set方法。
                    document.getElementById('model').value = value;
                },
                get:function(){
                    return results;
                }
            })
        </script>
    </body>
</html>
```
* 将上述代码copy到自己本地，打开页面，按F12打开console，在console中修改model.results的值，你会发现，只要model.results发生了修改，就会触发set方法将输入框中的值改变，实现了Vue中watch方法的效力。
* 参考MDN [Object.defineProperty()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/defineProperty)
