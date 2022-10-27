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

- <img src="https://i.ibb.co/DwPWVZ6/2022-10-27-15-34-29.png" alt="avatar" style="zoom:20%;" />

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

- <img src="https://i.ibb.co/jDw0G90/2022-10-27-15-41-15.png" alt="avatar" style="zoom:50%; width:750px" />

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
  
- #### ②部分实验代码：

  ```java
  public boolean onCreateOptionsMenu (Menu menu){
      getMenuInflater().inflate(R.menu.menu_demo, menu);
      return super.onCrateOptionsMenu(menu);
  }
  ```

- #### 实验结果如下图：

- <img src="https://i.ibb.co/71cBQmt/03-3.png" alt="avatar" style="zoom:50%; width:750px" />

### 4.ActionMode的上下文菜单

- #### 思路：

  ①创建菜单样式menu_blank

  ②ActionModeActivity中注册View，实现ActionMode.callback回调

- #### 部分代码：

  ```java
  public void onCreateContextMenu(ContextMenu menu, View v,
                                  ContextMenuInfo menuInfo) {
      super.onCreateContextMenu(menu, v, menuInfo);
      MenuInflater inflater = getMenuInflater();
      inflater.inflate(R.menu.menu_blank, menu);
  }
  
  ……………………
      
  ActionMode.Callback callback = new ActionMode.Callback()
      {
  
          @Override
          public boolean onCreateActionMode(ActionMode actionMode, Menu menu)
          {
              getMenuInflater().inflate(R.menu.menu_blank, menu);
              return true;
          }
  
          …………
  
          @Override
          public boolean onActionItemClicked(ActionMode actionMode, MenuItem menuItem)
          {
              actionMode.setTitle(selected_items + " selected");
              return true;
          }
      	
      	…………
      	
      };
  ```

- #### 实验结果如下图：

- <img src="https://i.ibb.co/5vkCL6H/03-4.png" alt="avatar" style="zoom:50%; width:750px" />

### 5.补充拓展

- 为方便进行测试，本实验还利用OnClick事件响应通过Intent进行Acitivity之间的跳转

- 本实验已有打包Exp_03.apk 已上传至云盘
- 链接：https://pan.baidu.com/s/17LbJ_3lf8NZbH8gEpNQseA 
  提取码：3ujx 

