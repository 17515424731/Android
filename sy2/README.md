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

### 2.自定义布局的AlertDialog

- #### 思路：

  ①layout文件中编写alert样式 

  ②通过AlertDialog.builder设置builder.setView

- #### ①部分实验代码：

  ```xml
  <TableLayout
          android:id="@+id/alert"
          android:layout_width="match_parent"
          android:layout_height="wrap_content"
          app:layout_constraintStart_toStartOf="parent"
          app:layout_constraintTop_toTopOf="parent">
  
          <TableRow
              android:layout_width="match_parent"
              android:layout_height="match_parent">
  
              <TextView
                  android:id="@+id/alert_title"
                  android:layout_width="match_parent"
                  android:layout_height="80dp"
                  android:layout_weight="1"
                  android:background="#FFE600"
                  android:fontFamily="cursive"
                  android:gravity="center"
                  android:textColor="@color/colorPrimary"
                  android:text="ANDROID APP"
                  android:textSize="24sp" />
          </TableRow>
  
          <TableRow
              android:layout_width="match_parent"
              android:layout_height="match_parent"
              android:gravity="center">
  
              <EditText
                  android:id="@+id/alert_username"
  					…………………………
  ```
  
- #### ②部分实验代码：

  ```java
     AlertDialog.Builder builder = new AlertDialog.Builder(this);
     builder.setView(View.inflate(this, R.layout.alert, null));
     builder.show();
  ```

- #### 实验结果如下图：

- <img src="https://i.ibb.co/52SFCfj/03-2.png" alt="avatar" style="zoom:50%; width:750px" />

### 3.使用XML定义菜单

- #### 思路：

  ①创建menu_demo.xml编写菜单样式

  ②在MenuActivity中装填对应的菜单并添加到menu中

- #### ①部分实验代码：

  ```xml
  <menu>
      <item android:title="字体大小">
          <menu >
              <item
                  android:id="@+id/font_small"
                  android:title="小" />
              <item
                  android:id="@+id/font_mid"
                  android:title="中" />
              <item
                  android:id="@+id/mi_big"
                  android:title="大" />
          </menu>
      </item>
  </menu>
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

