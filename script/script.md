1. script 属性
   
+ src : 要引用的js 文件路径
+ crossorigin： 跨域引用
  
  value:

    + anonymous 


            <script src="https://polyfill.io/v3/polyfill.js" crossorigin="anonymous"></script>
    + use-credentials: 

        服务端需要设置Access-Control-Allow-Origin

            <script src="https://polyfill.io/v3/polyfill.js" crossorigin="use-credentials"></script>
+ defer :延迟执行，当页面所有代码执行完毕才执行
  
  只针对外链脚本起作用。
+ async: 异步加载，加载完成立即执行
+ type: 
  
+ text/javascript:
+ module:

代码被视为es6 模块，可以使用import 和 default

2. 动态创建script 

        var script = document.createElement('script');

        // 设置script 属性

        script.src = "a.js";

        script.async = false;

        // 加载

        document.head.appendChild(script);
    
        常用来做jsonp ,因为本事script 就可以调用第三方的链接，比如cdn


3. 建议使用外部链接或CDN
   
+ 可维护性： 直接内联在页面上，可维护性太低
+ 缓存： 使用浏览器缓存，页面跳转时使用相同js 文件的，会直接从浏览器缓存中取，不会再去服务器请求。
+ 并发请求资源

4. onload 加载完毕，ie 下的onreadystatechange

        var script = document.createElement('script')

        script.src = 'a.js'

        script.onload=script.onreadystatechange=function(){
            if(!this.readyState || 
                this.readyState=='loaded' || 
                this.readyState=='complete'
              ){
                alert('onload')
            }            
        }

