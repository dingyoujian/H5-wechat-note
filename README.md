#### H5相关

#### navigator.userAgent

声明了浏览器用于 HTTP 请求的用户代理头的值
```js

UserAgent = navigator.userAgent.toLowerCase();

```
>根据userAgent判断操作系统

```js

/ipad/.test(UserAgent)
/iphone os/.test(UserAgent)
/android/.test(UserAgent)
/windows ce/.test(UserAgent)
/windows mobile/.test(UserAgent) //winmobile
/windows nt 5.0/.test(UserAgent) //win2K
/windows nt 5.1/.test(UserAgent) //xp
/windows nt 6.0/.test(UserAgent) //vista
/windows nt 6.1/.test(UserAgent) //win7
/windows nt 6.2/.test(UserAgent) //win8
/windows nt 6.3/.test(UserAgent) //win81

```

>根据userAgent判断浏览器

```js

/ucweb/.test(UserAgent)
/chrome/.test(UserAgent.substr(-33,6))
/firefox/.test(UserAgent)
/opera/.test(UserAgent)
/safari/.test(UserAgent) && !/chrome/.test(UserAgent)
/360se/.test(UserAgent)
/bidubrowser/.test(UserAgent)
/metasr/.test(UserAgent) //搜狗
/msie 6.0/.test(UserAgent) --- /msie 11.0/.test(UserAgent)
/lbbrowser/.test(UserAgent) //猎豹
/micromessenger/.test(UserAgent) //微信
/qqbrowser/.test(UserAgent)

```

#### popstate

popstate可以监控浏览器的返回和前进事件，但是对pushstate,replacestate操作无法监控到

>处理微信返回事件

首先先添加一条空白记录

```js

window.history.pushState('forward', null, '#');

```
然后增加监控

```js

window.addEventListener('popstate', function() {
    var hashLocation = location.hash;
    //在这里可以做一系列操作，监控到微信返回之后如果不跳转继续留在当前页可以再向history栈中压入一层记录
    //window.history.pushState('forward', null, '#'); 这样可以继续持续监听当前页
});

```

#### px2rem

flexible.js方案 sass混合
