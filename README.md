# KotlinAndroidLib [![](https://jitpack.io/v/VictorChow/KotlinAndroidLib.svg)](https://jitpack.io/#VictorChow/KotlinAndroidLib)

一些Android开发的扩展。

[[点这查看所有支持的扩展API(readmore)]](./DETAIL.md)

## Usage

```kotlin
//初始化
Ext.with(application)
```

## Gradle

```groovy
allprojects {
    repositories {
        ...
        maven { url 'https://jitpack.io' }
    }
}
```

```groovy
//依赖项
//org.jetbrains.kotlin:kotlin-stdlib-jre
//com.android.support:appcompat-v7

dependencies {
    compile 'com.github.VictorChow:kotlin-android-lib:1.1.1'
}
```

## Brief

### ViewExt

```kotlin
//设置padding
fun View.setPaddingLeft(value: Int) 
fun View.setPaddingRight(value: Int)
fun View.setPaddingTop(value: Int)
fun View.setPaddingBottom(value: Int)
fun View.setPaddingStart(value: Int)
fun View.setPaddingEnd(value: Int)
fun View.setPaddingHorizontal(value: Int)
fun View.setPaddingVertical(value: Int)

//设置宽高
fun View.setWidth(value: Int)
fun View.setHeight(value: Int)
fun View.resize(width: Int, height: Int)

//设置宽高(动画)
fun View.animateWidth(toValue: Int, duration: Long, interpolator: Interpolator)
fun View.animateWidthBy(toValue: Int, duration: Long, interpolator: Interpolator)
fun View.animateHeight(toValue: Int, duration: Long, interpolator: Interpolator)
fun View.animateHeightBy(toValue: Int, duration: Long, interpolator: Interpolator)

//移动
fun View.animateX(toValue: Int, duration: Long, interpolator: Interpolator)
fun View.animateXBy(toValue: Int, duration: Long, interpolator: Interpolator)
fun View.animateY(toValue: Int, duration: Long, interpolator: Interpolator)
fun View.animateYBy(toValue: Int, duration: Long, interpolator: Interpolator)

//ViewGroup子View
val ViewGroup.children: List<View>

//下划线
fun TextView.underLine()
//中划线
fun TextView.deleteLine()
//加粗
fun TextView.bold()

//setText getText
var EditText.value: String
//所有字母大写
fun EditText.uppercase()
//所有字母小写
fun EditText.lowercase()
//显示、隐藏密码
fun EditText.passwordToggledVisible()

//点击, 调用时lambda里的it为具体View类型
fun <T : View> T.click(block: (T) -> Unit) 
fun <T : View> T.longClick(block: (T) -> Boolean)

//显示
fun View.visiable()
fun View.invisiable()
fun View.gone()
fun View.visiableIf(block: () -> Boolean) 
fun View.invisiableIf(block: () -> Boolean) 
fun View.goneIf(block: () -> Boolean) 

//获取view的bitmap
fun View.getBitmap(): Bitmap
```

### CommonExt

```kotlin
val app: Application
val currentTimeMillis: Long

//三目运算符 yes no
val s = bool yes "yes" no "no"
val s = bool.yes("yes").no("no")
...
```

### DisplayExt

```kotlin
//屏幕尺寸、密度
val screenWidth: Int
val screenHeight: Int
val screenDensity: Float
val scaledDensity: Float
...
```

### DateTimeExt

```kotlin
//格式化日期
fun Long.date(pattern: String = "yyyy-MM-dd HH:mm:ss")
fun Long.year()
fun Long.month()
fun Long.day()
...
```

### StringExt

```kotlin
fun String.toast()
fun String.md5()
fun String.sha1()
...
```

### ListenerExt

```kotlin
fun Animator.addListener {
    onStart { }
    onCancel { }
    onEnd { }
    onRepeat { }
}

fun Animator.addPauseListener {
    onPause { }
    onResume { }
}
...
```

### ManagerExt

```kotlin
//直接调用
val connectivityManager
val alarmManager
val telephonyManager
val activityManager
...
```

### SharedPreferencesExt

```kotlin
fun spSetInt(key: String, value: Int)
fun spGetInt(key: String, defaultValue: Int = 0)
...
```

### BitmapExt

```kotlin
//bitmap转base64
fun Bitmap.toBase64(): String
//bitmap调整大小
fun Bitmap.resize(w: Number, h: Number): Bitmap
...
```

### FileExt

```kotlin
//复制文件
fun File.copy(dest: File)
//移动文件
fun File.move(dest: File)
...
```

### SpannableExt

```kotlin
//改变字符串中个别字体大小
fun spannableSize(text: String, textSize: Int, isDip: Boolean, start: Int, end: Int)
//字符串中个别字体加粗
fun spannableBold(text: String, start: Int, end: Int)
//改变字符串中个别字体颜色
fun spannableColor(text: String, @ColorRes colorId: Int, start: Int, end: Int)
```

### ToastExt

```kotlin
fun toast(msg: Any, isShortToast: Boolean = true) 
```

### ActivityExt

```kotlin
fun Activity.goActivity<T>()
fun Activity.goActivity<T>(requestCode: Int)

fun Activity.goService<T>()
fun Activity.goService<T>(sc: ServiceConnection, flags: Int)
...
```

### FragmentExt (support.v4)

```kotlin
fun Fragment.goActivity<T>()
fun Fragment.goActivity<T>(requestCode: Int)
...
```

### ActivityMgr

```kotlin
//建议放在BaseActivity里，onCreate()里ActivityMgr.add，onDestroy()里ActivityMgr.remove
fun add(activity: Activity)
fun remove(activity: Activity)
fun removeAll()
...
```

### ApiExt

```kotlin
// aboveApi(20) { view.elevation = 10f }
fun aboveApi(api: Int, included: Boolean = false, block: () -> Unit)
fun belowApi(api: Int, included: Boolean = false, block: () -> Unit)
```

[[点这查看所有支持的扩展API(readmore)]](./DETAIL.md)
