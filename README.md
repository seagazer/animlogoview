# AnimLogoView
Animtion view to show logo name.
[![](https://www.jitpack.io/v/seagazer/animlogoview.svg)](https://www.jitpack.io/#seagazer/animlogoview)

This library is separated from widgets of library sui, see more widgets from https://github.com/seagazer/sui.


How to use:
```java
// step1. add config in build.gradle of the root project
allprojects {
    repositories {
        maven { url 'https://www.jitpack.io' }
        google()
        jcenter()
    }
}

// step2. add the library in your app module
implementation 'com.github.seagazer:animlogoview:1.0.1'

// step3. define in layout xml
    <com.seagazer.animlogoview.AnimLogoView
        android:id="@+id/anim_logo"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        app:gradientAnimDuration="2000"
        app:gradientColor="@color/colorAccent"
        app:logoName="Seagazer"
        app:offsetAnimDuration="1500"
        app:showGradient="true"
        app:autoPlay="false"
        app:textColor="@color/colorPrimary"
        app:textSize="30sp"
        app:verticalOffset="50dp" />

// step4. add animation listener and start animation
    AnimLogoView animLogoView = findViewById(R.id.anim_logo);
    animLogoView.addOffsetAnimListener(new AnimatorListenerAdapter() {
        @Override
        public void onAnimationEnd(Animator animation) {
            Log.d("MainActivity", "Offset anim end");
        }
    });
    animLogoView.addGradientAnimListener(new AnimatorListenerAdapter() {
        @Override
        public void onAnimationEnd(Animator animation) {
            Log.d("MainActivity", "Gradient anim end");
        }
    });
    animLogoView.startAnimation();
```

<img src="https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/efc477d939c44fa78764826c8dcf5d67~tplv-k3u1fbpfcp-watermark.image" width = "430" height = "960" align=center />