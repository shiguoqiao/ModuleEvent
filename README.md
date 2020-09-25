ModuleEvent

ModuleEvent是一款Android组件化消息总线，基于LiveData，具有生命周期感知能力，支持Sticky，支持AndroidX，支持跨进程，支持跨APP


在工程中引用
Via Gradle:

implementation 'com.github.shiguoqiao.ModuleEvent:moduleevent:1.0.1'
annotationProcessor "com.github.shiguoqiao.ModuleEvent:compiler:1.0.1"


配置
在Application.onCreate方法中配置：

LiveEventBus
        .config()
        ...
lifecycleObserverAlwaysActive 配置LifecycleObserver（如Activity）接收消息的模式（默认值true）

autoClear 配置在没有Observer关联的时候是否自动清除LiveEvent以释放内存（默认值false）


混淆规则
-dontwarn com.jeremyliao.liveeventbus.**
-keep class com.tt52.moduleevent.liveeventbus.** { *; }
-keep class android.arch.lifecycle.** { *; }
-keep class android.arch.core.** { *; }
for androidx:

-dontwarn com.jeremyliao.liveeventbus.**
-keep class com.tt52.moduleevent.liveeventbus.** { *; }
-keep class androidx.lifecycle.** { *; }
-keep class androidx.arch.core.** { *; }
