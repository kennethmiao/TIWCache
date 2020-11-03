# Android

TIWCache 对外提供原生 WebView 和 WebViewClient 的子集，使用方式和原生 WebView 无差别。

第一步、添加依赖 TIWCache
```
implementation 'com.tencent.tiw.cache:TIWCache:1.0.0.0'
```

第二步、设置配置
```
TIWCacheConfig config = new TIWCacheConfig();
config.dir = getFilesDir().toString();
TIWCacheManager.getInstance(this).setConfig(config);
```

第三步、创建 TIWWebView

* XML 创建

```
//1. 添加XML代码
<com.tencent.tiw.cache.TIWWebView
    android:id="@+id/webview"
    android:layout_width="match_parent"
    android:layout_height="match_parent">
</com.tencent.tiw.cache.TIWWebView>
// 2. 获取TIWWebView
this.webView = findViewById(R.id.webview);
```


* 代码创建
```
this.webView = new TIWWebView(this);
```

第四步、设置TIWWebViewClient

```
this.webView.setWebViewClient(new TIWWebViewClient());
```

通过以上三步，您已经完成了 TIWCache 的集成。



# iOS

TIWCache 对外提供原生 WebView 和 WebViewClient 的子集，使用方式和原生 WebView 无差别。

第一步、CocoaPods 添加依赖 TIWCache
```
pod 'TIWCache_iOS','1.0.0.0'
```

第二步、设置配置

```
TIWCacheConfig *config = [[TIWCacheConfig alloc] init];
config.dir = NSSearchPathForDirectoriesInDomains(NSCachesDirectory, NSUserDomainMask, YES)[0];
[[TIWCacheManager shareInstance] setConfig:config];
```

第三步、创建 TIWWebView

```
TIWWebViewConfiguration *webConfig = [[TIWWebViewConfiguration alloc] init];
TIWWebView webView = [[TIWWebView alloc] initWithFrame:self.view.bounds configuration:webConfig];
```

通过以上三步，您已经完成了 TIWCache 的集成。