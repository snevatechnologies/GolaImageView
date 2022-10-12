# GolaImageView

===============

A fast circular image view library developed by Sneva Technologies to help developers to create circular image

![GolaImageView](https://github.com/snevatechnologies/GolaImageView/blob/d1bb8b173067efe711848934daff25bb11f6eb31/photo_6213068565221846988_y.jpg)

You can use any library like Glide or Picasso to show image in this GolaImageView

Gradle
------
```
allprojects {
	repositories {
		...
		maven { url 'https://jitpack.io' }
	}
}
```
```
dependencies {
	...
	implementation 'com.github.snevatechnologies:golaimageview:1.1'
}
```

Usage
-----
```xml
<com.sneva.gola.GolaImageView
        android:id="@+id/golaImageView"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:elevation="15dp"
        app:gola_circle_background_color="@color/white"
        app:gola_border_width="3dp"
        app:gola_border_color="@color/white"
        android:src="@drawable/placeholder"
        tools:targetApi="lollipop" />
```

Limitations
-----------
* The ScaleType is always CENTER_CROP and you'll get an exception if you try to change it. This is (currently) by design as it's perfectly fine for profile images.
* Enabling `adjustViewBounds` is not supported as this requires an unsupported ScaleType
* If you use an image loading library like Picasso or Glide, you need to disable their fade animations to avoid messed up images. For Picasso use the `noFade()` option, for Glide use `dontAnimate()`. If you want to keep the fadeIn animation, you have to fetch the image into a `Target` and apply a custom animation yourself when receiving the `Bitmap`.
* Using a `TransitionDrawable` with `CircleImageView` doesn't work properly and leads to messed up images.
