1. script 可以放在任意位置，但是涉及到dom 的操作，一定要dom 元素先加载了才能执行
   
因为javascript是单线程的

        <script>

            document.getElementById('id')
        
        </script>

        <div id="id"></div>

        UI 是单线程解析，从上而下，先解析js, 里面获取id 为 'id' 的元素，而此时id 还没有渲染，从而取不到，得到一个null

2. 解决方案：

+ 放到dom 后面，保证dom 的渲染
+ 使用dom 事件
  
        window.onload = function(){
            // 页面全部加载完毕，包括页面资源（图片，视频）
        }

        document.addEventListener( "DOMContentLoaded", function(){
            dom 元素加载完毕
        }, false );

3. 建议方案
   
把script 放到body 最下面，保证dom 加载完毕，

优点：

+ 单线程会阻塞UI的渲染，造成白屏时间太长
+ js 即使错误也不影响页面的渲染