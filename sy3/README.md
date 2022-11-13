# Exp_03 Android界面组件实验

### 1. Android ListView的用法

- #### 思路

  ①利用SimpleAdapter实现如下界面效果

  ②（1）注意列表项的布局（2）图片使用QQ群附件资源（3）使用Toast显示选中的列表项信息

### 2.创建自定义布局的AlertDialog

- #### 思路：

  ①调用AlertDialog.Builder对象上的setView()将布局添加到AlertDialog。

  ②通过AlertDialog.builder设置builder.setView

### 3.使用XML定义菜单

- #### 思路：

  ①使用xml定义Menu，在MenuActivity中装填对应的菜单并添加到menu中

  ②创建上下文操作模式(ActionMode)的上下文菜单，使用ListView或者ListActivity创建List，为List Item创建ActionMode形式的上下文菜单

- #### ①部分实验代码：

  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    tools:context=".ActionModeActivity">

    <ListView
        android:id="@+id/LV_am_demo"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

  </androidx.constraintlayout.widget.ConstraintLayout>
  ```
  
  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <ListView
        android:id="@+id/LV_demo"
        android:layout_width="match_parent"
        android:layout_height="match_parent"/>

  </androidx.constraintlayout.widget.ConstraintLayout>
  ```
   
  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    xmlns:app="http://schemas.android.com/apk/res-auto">

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

  ```

- #### ②部分实验代码：

  ```java
  public void click_select (View V) throws Exception{
        LinearLayout list_unit = V.findViewById(R.id.list_unit_01);
        TextView name = V.findViewById(R.id.list_unit_01_name);
            if (view_select.get(V) == null || !view_select.get(V)) {
                list_unit.setBackgroundColor(Color.BLUE);
                view_select.put(V, true);
                Toast toast = Toast.makeText(MainActivity.this, name.getText(), Toast.LENGTH_SHORT);
                toast.show();
            } else {
                list_unit.setBackgroundColor(Color.WHITE);
                view_select.put(V, false);
                AlertDialog.Builder builder = new AlertDialog.Builder(this);
                builder.setView(View.inflate(this, R.layout.alert, null));
                builder.show();
            }
  ```
  
   ```java
  public boolean onCreateOptionsMenu(Menu m)
    {
        this.getMenuInflater().inflate(R.menu.menu_demo, m);

        return true;
    }
  ```
  
   ```java
  public void useAppContext() {
        // Context of the app under test.
        Context appContext = InstrumentationRegistry.getInstrumentation().getTargetContext();
        assertEquals("com.sueed.exp_03", appContext.getPackageName());
    }
  ```

- #### 实验结果如下图：

- <img src="https://github.com/17515424731/Android/blob/main/image/sy3-01.png" alt="avatar" style="zoom:50%; width:750px" />

- <img src="https://github.com/17515424731/Android/blob/main/image/sy3-02.png" alt="avatar" style="zoom:50%; width:750px" />

- <img src="https://github.com/17515424731/Android/blob/main/image/sy3-03.png" alt="avatar" style="zoom:50%; width:750px" />

- <img src="https://github.com/17515424731/Android/blob/main/image/sy3-04.png" alt="avatar" style="zoom:50%; width:750px" />

- <img src="https://github.com/17515424731/Android/blob/main/image/sy3-05.png" alt="avatar" style="zoom:50%; width:750px" />

- <img src="https://github.com/17515424731/Android/blob/main/image/sy3-06.png" alt="avatar" style="zoom:50%; width:750px" />

- <img src="https://github.com/17515424731/Android/blob/main/image/sy3-07.png" alt="avatar" style="zoom:50%; width:750px" />

- <img src="https://github.com/17515424731/Android/blob/main/image/sy3-08.png" alt="avatar" style="zoom:50%; width:750px" />

- <img src="https://github.com/17515424731/Android/blob/main/image/sy3-09.png" alt="avatar" style="zoom:50%; width:750px" />
