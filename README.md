# PageStatus
效果图

<img width="50%" height="50%" src="https://github.com/Xiaohy61/PageStatus/blob/master/2018-01-05_11_00_30.gif"/>

### 依赖：

``` xml
allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }

		}
	}
```
``` xml
  dependencies {

	    compile 'com.github.Xiaohy61:PageStatus:1.0.1'

	}

```

### 配置
1. 可以在application全局配置：

```xml
public class App extends Application {

    @Override
    public void onCreate() {
        super.onCreate();
        //图片，文字，文字颜色都可以自己配置，或者只配置文字
        new PageStatus.Builder()
                .setLoadingTipText("数据加载中...")
                .setInternetErrorText("网络出现错误...")
                .setBtnRetryText("点我重试")
                .setErrorTipText("发生错误...")
                .setNoDataTipText("抱歉暂无相关数据!");
    }
}
```
2.或者在xml中配置：
```xml
 <com.skyward.pagestatus.PageStatus
        android:id="@+id/page_status_layout"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        app:noDataTipText="抱歉，暂无数据">
        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Hello World!"
            app:layout_constraintBottom_toBottomOf="parent"
            app:layout_constraintLeft_toLeftOf="parent"
            app:layout_constraintRight_toRightOf="parent"
            app:layout_constraintTop_toTopOf="parent"/>
    </com.skyward.pagestatus.PageStatus>
```
