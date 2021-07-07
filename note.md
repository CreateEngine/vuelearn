### vue 源码学习
#### vue版本 **v2.6.14**
1. Object.defineProperty
   [参考文章](https://juejin.cn/post/6844903710410162183)
   > Object.defineProperty(obj,prop,descriptor)

    * `obj: 要在其上定义属性的对象`
    * `prop: 要定义或修改的属性的名称`
    *  `descriptor: 将被定义或修改的描述符`
  
        ```javascript
        var obj = {},value=null;
        Object.defineProperty(obj,'num',{
            value : 1, // value 与get不可同时存在
            writable : true, // writable 与set不可同时存在
            enumerable : true,
            configurable : true,
            get: function(){
                console.log('执行了 get 操作')
                return value;
            },
            set: function(newValue) {
                console.log('执行了 set 操作')
                value = newValue;
            } 
        })
        ```
2. Proxy

  
  