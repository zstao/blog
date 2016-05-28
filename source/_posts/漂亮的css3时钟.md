title: 漂亮的css3时钟
date: 2015-09-01 12:59:39
tags: [前端, css, JavaScript]
---

>这是一个漂亮的时钟

[在线demo](http://zstao.tk/demo/css/clock.html)

<iframe src="http://zstao.tk/demo/css/clock.html" scrolling="no" marginheight="600px" width="100%" height="310px"></iframe>

<!--more-->

源码如下：
```
<style>
        * {
            margin: 0;
            padding: 0;
        }

        #box {
            width: 300px;
            height: 300px;
            border: solid 1px #000;
            border-radius: 50%;
            position: absolute;
            top: 50%;
            left: 50%;
            margin-left: -150px;
            margin-top: -150px;
            box-shadow: 1px 1px 5px #000;
            cursor: pointer;
        }

        .hour {
            width: 14px;
            height: 80px;
            background: #000;
            position: absolute;
            top: 50%;
            left: 50%;
            margin: -80px 0 0 -7px;
            border-radius: 50% 50% 0 0;
            transform-origin: center bottom;
        }

        .min {
            width: 14px;
            height: 100px;
            background: #000;
            position: absolute;
            top: 50%;
            left: 50%;
            margin: -100px 0 0 -7px;
            border-radius: 50% 50% 0 0;
            transform-origin: center bottom;
        }

        .sec {
            width: 4px;
            height: 120px;
            background: red;
            position: absolute;
            top: 50%;
            left: 50%;
            margin: -120px 0 0 -2px;
            transform-origin: center bottom;
        }

        .cap {
            width: 20px;
            height: 20px;
            background: #999;
            border-radius: 50%;
            position: absolute;
            top: 50%;
            left: 50%;
            margin: -10px 0 0 -10px;
        }

        .scale {
            width: 4px;
            height: 10px;
            background: #000;
            position: absolute;
            left: 50%;
            margin-left: -2px;
            display: block;
            -webkit-transform: rotate(45deg);
            transform-origin: center 150px;
        }

        .bs {
            width: 6px;
            height: 18px;
            background: #000;
            position: absolute;
            left: 50%;
            margin-left: -3px;
            display: block;
            -webkit-transform: rotate(45deg);
            transform-origin: center 150px;
        }

        .bs em {
            width: 50px;
            text-align: center;
            margin: 17px 0;
            position: absolute;
            top: 0;
            left: 50%;
            margin-left: -25px;
            font-style: normal;
        }
    </style>
    <script>
        window.onload = function(){
            var oBox = document.getElementById('box');
            var oH = document.querySelector('.hour');
            var oM = document.querySelector('.min');
            var oS = document.querySelector('.sec');

            //生成刻度 - 整点
            var N = 60;
            for(var i = 0; i<N ; i++){
                var oSpan = document.createElement('span');

                if(i%5 == 0){
                    oSpan.className = 'bs';
                    var num = i/5==0 ? 12:i/5;
                    oSpan.innerHTML = '<em>'+ num +'</em>'
                    oSpan.style.transform = 'rotate('+ (i*N) +'deg)';
                    oSpan.children[0].style.transform = 'rotate('+ -i*6 +'deg)'

                }else{
                    oSpan.className = 'scale';
                }

                oBox.appendChild(oSpan);
                oSpan.style.transform = 'rotate('+ 6 * i+'deg)'
            }

            //设置时间
            function clock(){
                var oDate = new Date();
                var h = oDate.getHours();
                var m = oDate.getMinutes()+1;
                var s = oDate.getSeconds();
                var ms=oDate.getMilliseconds();

                oH.style.transform='rotate('+(h*30+m/60*30)+'deg)';
                oM.style.transform='rotate('+(m*6+s/60*6)+'deg)';
                oS.style.transform='rotate('+(s*6+ms/1000*6)+'deg)';
            }
            clock();
            setInterval(clock,30);
        }
    </script>
</head>

<div id="box">
    <div class="hour"></div>
    <div class="min"></div>
    <div class="sec"></div>
    <div class="cap"></div>
</div>
```

