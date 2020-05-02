# Android混淆打包
## 关闭Logcat

1. 在proguard-rules.pro文件添加
```
-assumenosideeffects class android.util.Log {
public static boolean isLoggable(java.lang.String,int);
public static int v(...);
public static int i(...);
public static int w(...);
public static int d(...);
public static int e(...);
}
```
意思是使代码无效

2. 在gradle文件中
```
 buildTypes {
        debug1 {
            proguardFiles getDefaultProguardFile('proguard-android-optimize.txt'), 'proguard-rules.pro' //定义混淆文件
            minifyEnabled true //开启混淆
        }
        }
```
把其中proguard-android.txt 替换成 proguard-android-optimize.txt。 

3. Android默认的混淆文件在~\SDK\tools\proguard中，有两个，一个执行了优化，一个没有。网上很多人讲，加了优化log的代码没用的原因，就是因为没有执行代码优化。


## 定义不混淆的内容
1. 不混淆bean包下的类
```
-keep class com.shenghuofan.bean.**{*;}
```
2. 待续。。。
3. 

## 多渠道打包
1. 待续。。。
2. 


## gradle定义签名
1. 在project structure的signing页，添加一个keystore，添加keystore的帐号密码
2. gradle文件会生成
```
 signingConfigs {
        config {
            keyAlias 'kechong'
            keyPassword 'liu314159'
            storeFile file('D:/Users/Desktop/kechong.keystore')
            storePassword 'liu314159'
        }
    }
```
可以把keystore放入项目中 `storeFile file('kechong.keystore')`,这样项目成员用的就是同一个keystore，比较方便。
3. gradle buildType添加
```
 buildTypes {
        debug1 {
        signingConfig signingConfigs.config
    }
```
4 .buider variants中选中打包的方式。





