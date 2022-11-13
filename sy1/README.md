# 实验一 Android开发基础

### 1. Android Studio下载及安装

- #### 思路

  ①下载地址：https://developer.android.com/studio
  
  https://developer.android.google.cn/studio/

  ②安装注意事项：Android Studio版本越高对于电脑硬件系统要求越高（但仍然推荐4.2以上版本）。如果硬件达不到要求，可以选择早前的几个版本，比如安装3.5版本等。
  
  
### 2.创建第一个Android工程并同步至GitHub

- #### 思路：

  ①注册GitHub账号，安装Git工具
  
  课程官方GitHub：https://github.com/fjnu-cse
  
  Git安装：https://git-scm.com/

  ②创建Android工程并同步至GitHub
  
  参考1：命令行方式，推荐
  
  http://blog.csdn.net/fjnu_se/article/details/66472625
  
  ③创建第一个Android工程并运行
  
- #### ①部分实验代码：

  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Hello World!"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

  </androidx.constraintlayout.widget.ConstraintLayout>
  					…………………………
  ```
  
- #### ②部分实验代码：

  ```java
     package com.example.test;
     import androidx.appcompat.app.AppCompatActivity;
     import android.os.Bundle;
     public class MainActivity extends AppCompatActivity {
     @Override
     protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        }
    }
  ```

- #### 实验结果如下图：

- <img src="image/HelloWorld.png" alt="avatar" style="zoom:50%; width:750px" />

