# 实验二 Android界面布局实验

### 1. 线性布局

- #### 思路

  ①layout文件中编写布局效果

- #### ①部分实验代码：

  ```xml
   <?xml version="1.0" encoding="utf-8" ?>
   <LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity"
    android:orientation="vertical">
    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="50dp"
        android:orientation="horizontal"
        >


        <TextView
            android:layout_width="0dp"
            android:layout_height="50dp"
            android:layout_weight="1"
            android:text="One,One"
            android:background="#4DB38A"
            android:textColor="#333333"
            android:textSize="12dp"
            android:gravity="center"
            />
        <TextView
            android:layout_width="0dp"
            android:layout_height="50dp"
            android:layout_weight="1.3"
            android:layout_marginLeft="3dp"
            android:text="One,Two"
            android:background="#4DB38A"
            android:textColor="#333333"
            ......
  ```

- #### 实验结果如下图：

- <img src="https://github.com/17515424731/Android/blob/main/image/LinearLayout.png" alt="avatar" style="zoom:20%;" />

### 2.表格布局

- #### 思路：

  ①layout文件中编写布局效果

- #### ①部分实验代码：

  ```xml
  <TableLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity"
    android:stretchColumns="1">

    <TableRow>
        <TextView
            android:text="Open...."
            android:paddingLeft="10dp"/>
        <TextView
            android:text="Ctrl+O"
            android:gravity="right"
            android:paddingRight="10dp"/>
    </TableRow>
  					…………………………
  ```

- #### 实验结果如下图：

- <img src="https://github.com/17515424731/Android/blob/main/image/TableLayout.png" alt="avatar" style="zoom:50%; width:750px" />

### 3.约束布局1

- #### 思路：

  ①layout文件中编写布局效果

- #### ①部分实验代码：

  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <androidx.constraintlayout.widget.Guideline
        android:id="@+id/guideline2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:orientation="horizontal"
        app:layout_constraintGuide_end="605dp" />

    <androidx.constraintlayout.widget.Guideline
        android:id="@+id/guideline3"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:orientation="horizontal"
        app:layout_constraintGuide_begin="553dp" />

    <Button
        android:id="@+id/button5"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginBottom="50dp"
        android:text="0"
        android:textSize="24sp"
        app:layout_constraintBottom_toTopOf="@+id/guideline3"
        app:layout_constraintEnd_toStartOf="@+id/button6"
        app:layout_constraintHorizontal_bias="0.5"
        app:layout_constraintStart_toStartOf="parent" />
  ```

- #### 实验结果如下图：

- <img src="https://github.com/17515424731/Android/blob/main/image/ConstraintLayout1.png" alt="avatar" style="zoom:50%; width:750px" />

### 4.约束布局2

- #### 思路：

  ①layout文件中编写布局效果

  ②MainActivity中编写java代码

- #### 部分代码：

  ```java
   private fun makeFullScreen() {
    // Remove Title
    requestWindowFeature(Window.FEATURE_NO_TITLE)

    // Make Fullscreen
    window.setFlags(WindowManager.LayoutParams.FLAG_FULLSCREEN,
        WindowManager.LayoutParams.FLAG_FULLSCREEN)

    // Hide the toolbar
    supportActionBar?.hide()
  }
  
  ……………………
      
  ```
  
  
  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <android.support.constraint.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center_horizontal"
    android:orientation="vertical"
    tools:context=".MainActivity">

  <ImageView
      android:id="@+id/spaceStationIcon"
      android:layout_width="30dp"
      android:layout_height="30dp"
      android:layout_marginTop="15dp"
      android:src="@drawable/space_station_icon"
      app:layout_constraintEnd_toStartOf="@+id/flightsIcon"
      app:layout_constraintHorizontal_chainStyle="spread"
      app:layout_constraintStart_toStartOf="parent"
      app:layout_constraintTop_toTopOf="parent" />

  <ImageView
      android:id="@+id/flightsIcon"
      android:layout_width="30dp"
      android:layout_height="30dp"
      android:src="@drawable/rocket_icon"
      app:layout_constraintBottom_toBottomOf="@+id/spaceStationIcon"
      app:layout_constraintEnd_toStartOf="@+id/roverIcon"
      app:layout_constraintStart_toEndOf="@+id/spaceStationIcon"
      app:layout_constraintTop_toTopOf="@+id/spaceStationIcon" />
  ```

- #### 实验结果如下图：

- <img src="https://github.com/17515424731/Android/blob/main/image/ConstraintLayout2.png" alt="avatar" style="zoom:50%; width:750px" />

