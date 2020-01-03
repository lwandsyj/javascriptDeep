1. JavaScript 中在es6 以前作用域是函数级别的，没有块级作用域
   

        function show(){
            var a=false;
            if(a){
                var c='zhangsan'；
            }
            console.log(c)
        }

        在有块级作用域的语言中，没有执行var c='zhangsan',
        是不会再函数中有c的定义，但是在JavaScript中作用域
        是函数级别的，变量声明会被提前到当前作用域的顶层，
        即和以下函数声明一样：

        function show(){
            var a=false;
            var c;
            if(a){
                c='zhangsan'
            }
            console.log(c);// undefined
        }

2. 变量提升只会提升变量的声明，不会提升变量的赋值。赋值时在运行期
3. 每个函数this 执行都会发生改变。
4. 有时候我们又需要this 明确对象，可以使用apply,call,bind 
5. 区别
   
+ apply,call 会执行函数，但是bind 返回一个改变了this 执行的函数
+ apply 绑定参数时一个数组或者类数组对象(比如arguments)
  
        fn.apply({},[12,23,34]);
        12 就是第一个传进去的参数
        23 就是第二个传进去的参数
        后面的一次类推
+ call 绑定参数是一个一个传进去的
  
        fn.call({},12,23,34)

        call 是一个一个传进去的，传入的为位置和在call 中一致

+ bind 可以传入参数，亦可以不传入参数，因为bind 返回的是一个函数，而不是立即执行
  
        let f=fn.bind({})

        f(12,23,34)

        或者

        let f=fn.bind({},23,34,45)

        f()

6. 声明
   
<strong>网上有些大神亲自测试过，call 的性能要优于apply,而且jquery 源码中也注释过call 的性能优于apply </strong>

<strong> 当参数超过三个以后，尤其明显</strong>

7. 所有的函数都可以调用call 和 apply， 同时，call 和 apply 一样是函数，也可以用apply 和 call 
   
