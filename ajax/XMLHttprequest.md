1. onreadystatechange : ajax 回调 

        // 判断 request.readyState==4 的效果等同于 onload 

        if(request.readyState==4 && request.status==200)

        {

            // 加载且响应正常完成后执行的代码.... 

        }

2. onload 是xhr leve2 中新增的