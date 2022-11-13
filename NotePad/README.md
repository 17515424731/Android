# NotePad Android期中实验

### 1. NoteList界面中笔记条目增加时间戳显示

- #### 思路

  ①（1）修改NotesList.java中PROJECTION的内容，添加modif字段，使其在后面的搜索中才能从SQLite中读取修改时间的字段。

  （2）实验代码：

  ```java
  private static final String[] PROJECTION = new String[] {
            NotePad.Notes._ID, // 0
            NotePad.Notes.COLUMN_NAME_TITLE, // 1
            //Extended:display time, color
            NotePad.Notes.COLUMN_NAME_MODIFICATION_DATE, // 2
    };
  ```
  ②（1）修改适配器内容，增加dataColumns中装配到ListView的内容，同时增加一个文本框来存放时间。
  
  （2）实验代码：
  
  ```java
  final String[] dataColumns = { NotePad.Notes.COLUMN_NAME_TITLE , NotePad.Notes.COLUMN_NAME_MODIFICATION_DATE} ;
  int[] viewIDs = { android.R.id.text1, R.id.text2};
  ```
  ③（1）修改layout文件夹中noteslist_item.xml的内容，增加一个textview组件，为他们添加一个布局。
  
  （2）实验代码：

  ```xml
  <LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:paddingLeft="6dip"
    android:paddingRight="6dip"
    android:paddingBottom="3dip">
 
 
    <TextView
        android:id="@android:id/text1"
        android:layout_width="match_parent"
        android:layout_height="?android:attr/listPreferredItemHeight"
        android:textAppearance="?android:attr/textAppearanceLarge"
        android:gravity="center_vertical"
        android:paddingLeft="5dip"
        android:singleLine="true"
        />
    <TextView
        android:id="@+id/text2"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:textAppearance="?android:attr/textAppearanceLarge"
        android:gravity="center_vertical"
        android:singleLine="true"
        />
  </LinearLayout>


  ```
  ④（1）修改NoteEditor.java中updateNote方法中的时间类型。
  
  （2）实验代码：
  
  ```java
  private final void updateNote(String text, String title) {
 
        // Sets up a map to contain values to be updated in the provider.
        ContentValues values = new ContentValues();
        Long now = Long.valueOf(System.currentTimeMillis());
        SimpleDateFormat sf = new SimpleDateFormat("yy/MM/dd HH:mm");
        Date d = new Date(now);
        String format = sf.format(d);
        values.put(NotePad.Notes.COLUMN_NAME_MODIFICATION_DATE, format);


  ```
  ⑤实验结果如下图：
  

- <img src="https://i.ibb.co/FJJw8HK/2022-10-27-16-51-40.png" alt="avatar" style="zoom:50%; width:750px" />：
- <img src="https://i.ibb.co/FJJw8HK/2022-10-27-16-51-40.png" alt="avatar" style="zoom:50%; width:750px" />
