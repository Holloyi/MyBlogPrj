---
title: Retrofit基本使用
tags: [Retrofit,Android,移动端,网络请求]
categories: Android
date: 2021-12-23
updated:  2021-12-23
description: Android中Retrofit网络情况框架的基本使用
top_img: https://static.runoob.com/images/mix/wallpaper.png
cover: https://static.runoob.com/images/mix/wallpaper.png
connents: 
aside: true
--- 


### Retrofit最佳实现

话不多说,直接上代码

#### 1.Rretrofit 封装

```java
public class ServiceGenerator {
    //服务器地址
    private static final String BASE_URL = "";

    //retrofit builder
    private static Retrofit.Builder builder = new Retrofit.Builder()
            .baseUrl(BASE_URL)
            .addConverterFactory(GsonConverterFactory.create());

    //retrofit object
    private static Retrofit retrofit = builder.build();

    //log interceptor 打印网络请求日志
    private static HttpLoggingInterceptor loggingInterceptor = new HttpLoggingInterceptor().setLevel(HttpLoggingInterceptor.Level.BODY);

    private static OkHttpClient.Builder httpClientBuilder = new OkHttpClient.Builder();


    //service generator 供外部调用
    public static <S> S createService(Class<S> serviceClass){
        //未添加拦截器 且 处于开发模式
        if (!httpClientBuilder.interceptors().contains(loggingInterceptor) && BuildConfig.DEBUG)
        {
            httpClientBuilder.addInterceptor(loggingInterceptor);
            builder = builder.client(httpClientBuilder.build());
            retrofit = builder.build();
        }
        return retrofit.create(serviceClass);
    }
}
```



#### 2.具体调用

```java
RequestService service = ServiceGenerator.createService(RequestService.class);
service.listDevices().enqueue(new Callback<BaseResponse<List<Device>>>() {
    @Override
    public void onResponse(Call<BaseResponse<List<Device>>> call, Response<BaseResponse<List<Device>>> response) {

    }

    @Override
    public void onFailure(Call<BaseResponse<List<Device>>> call, Throwable t) {

    }
});
```

