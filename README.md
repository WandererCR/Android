# midtest  
期中实验报告：
实验要求：
 基本要求：每个人必须完成
     NoteList中显示条目增加时间戳显示
     添加笔记查询功能（根据标题查询）
◼ 附加功能：根据自身实际情况进行扩充，以下是建议的扩展功能（拟作
为期末作业）
     UI美化
     更改记事本的背景
     导出笔记，笔记的云备份和恢复
     添加代办功能
     记事本的设置的功能
     笔记分类
     支持多种资源，如保存图片、语音、视频等（参考印象笔记）
     语音搜索？
     笔记便签
     偏好设置
    
    1，添加时间戳显示：
 NoteList使用SimpleCursorAdapter来装配数据，首先查询数据库的内容

 Cursor cursor = managedQuery(
         getIntent().getData(),           
         PROJECTION,                      
         null,                             
         null,                             
         NotePad.Notes.DEFAULT_SORT_ORDER);

然后通过SimpleCursorAdapter来进行装配

 SimpleCursorAdapter adapter
         = new SimpleCursorAdapter(
                   this,                             
                   R.layout.noteslist_item,          
                   cursor,                           
                   dataColumns,
                   viewIDs);
添加时间戳的位置在主页面的每个列表项中添加，即在notelist_item.xml布局文件中添加

   <TextView  
       android:id="@android:id/text2"  
       android:layout_width="match_parent"  
       android:layout_height="wrap_content"  
       android:textAppearance="?android:attr/textAppearanceLarge"  
       android:gravity="center_vertical"  
       android:paddingLeft="5dp"  
       android:singleLine="true" />  `
实验截图：
![image](https://github.com/peach7k/midtest/blob/main/Android%E5%9B%BE%E7%89%87/%E6%97%B6%E9%97%B4%E6%88%B3.png)

2.查询功能：
 a.在list_options_menu.xml布局文件中添加搜索功能
<item
      android:id="@+id/menu_search"
      android:icon="@android:drawable/ic_menu_search"
      android:title="@string/menu_search"
      android:showAsAction="always" />
  b.新建一个查找笔记内容的布局文件
  c.NoteList类中的onOptionsItemSelected方法中添加search查询的处理(跳转)
  d.新建一个NoteSearch类用于search功能的功能实现
  具体源码看文件
  
  实验截图：![image](https://github.com/peach7k/midtest/blob/main/Android%E5%9B%BE%E7%89%87/%E6%9F%A5%E6%89%BE.png
)

附加功能：
UI 设计：
![image](https://github.com/peach7k/midtest/blob/main/Android%E5%9B%BE%E7%89%87/UI.png
)

更换背景颜色：基础为白色
实验截图：![image](https://github.com/peach7k/midtest/blob/main/Android%E5%9B%BE%E7%89%87/%E7%AC%94%E8%AE%B0%E5%88%86%E7%B1%BB.png)

笔记分类：

实验截图：![image](https://github.com/peach7k/midtest/blob/main/Android%E5%9B%BE%E7%89%87/%E7%AC%94%E8%AE%B0%E5%88%86%E7%B1%BB.png)


