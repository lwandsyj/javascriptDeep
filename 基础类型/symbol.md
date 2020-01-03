1. symbol 是唯一的，可用作对象的唯一属性名。
2. symbol 永远都是唯一的，即使使用相同的变量和值，生成的值也不相同。

        let x = Symbol(123)
        let y = Symbol(123)

        x === y  // =====> false

3. Symbol 作为object 的key 值是，不能被for ...in 和 Object.keys 获取
   
4. Object.getOwnPropertySymbols, 获取Symbol 类型的key ,返回一个数组
   
        let array = Object.getOwnPropertySymbols(obj);

5. Symbol.for(key)
   
   第一次如果没有则创建，第二次用时为获取值

        let x = Symbol('name')  // 第一次没有name 键值，创建

        let y = Symbol('name')  // 第二次前面已经创建了，表示已经有了name 键值，这里表示获取
        x===y   true

6. Symbol.keyFor()