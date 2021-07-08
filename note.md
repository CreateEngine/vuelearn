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
   [参考文章](https://juejin.cn/post/6844904090116292616)
   > var proxy = new Proxy(target,handler);

   * `proxy 可以拦截多达13种操作`
   * `proxy 与 reflect 同时使用`

   ```javascript
   var proxy = new Proxy({},{
       get(obj,prop){
           console.log('设置 get 操作')
           return obj[prop]
       },
       set(obj,prop,value){
           console.log('设置 set 操作')
           obj[prop] = value;
       }
   })
   ```
  
  