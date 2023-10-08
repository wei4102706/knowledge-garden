
[Retrofit](https://square.github.io/retrofit/)是專為API連線而生的第三方套件，與API連線的效率非常高，最特別的是其規範的REST框架讓程式高度解耦，好寫易維護，被譽為API連線的教科書。另外它跟OkHttp同為Square公司出品，兩者可以完美整合發揮更多功能。

## 加入dependencies

```
compile 'com.squareup.retrofit2:retrofit:2.1.0'
compile 'com.squareup.retrofit2:converter-gson:2.1.0'
```

第一行是Retrofit本體，第二行是用Google的Gson套件作為資料處理的converter，Retrofit都整合好了所以我們之後只要一行程式碼就能用Gson處理資料