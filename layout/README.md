# 实验二：Android UI开发

## 一、布局类型

1.线性布局：

* 线性布局（Linearlayout）在实际开发中比较常用，它主要以水平和垂直方式来显示界面中的控件。当控件水平排列时，先是顺序依次为从左到右；当控件垂直排列时，显示顺序依次为从上到下。
* 属性：
  * orientation:用于控制控件方向。
  * vertical:表示线性布局垂直显示。
  * horizontal:表示线性布局水平显示。

2.性对布局：

* 相对布局（RelativeLayout）是通过相对定位的方式指定控件位置，即以其他控件或父容器为参照物，摆件控件位置。在设计相对布局时要遵循控件之间的依赖关系，后放入控件的位置依赖于放入的控件。
* 属性：
  * 相对于父组件：
    * android:layout_alignParentTop      如果为true,将该控件的顶部与其父控件的顶部对齐;   
    * android:layout_alignParentBottom 如果为true,将该控件的底部与其父控件的底部对齐;   
    * android:layout_alignParentLeft      如果为true,将该控件的左部与其父控件的左部对齐;   
    * android:layout_alignParentRight    如果为true,将该控件的右部与其父控件的右部对齐;  
  * 相对于给定ID控件  
    * android:layout_above 将该控件的底部置于给定ID的控件之上;   
    * android:layout_below 将该控件的底部置于给定ID的控件之下;   
    * android:layout_toLeftOf    将该控件的右边缘与给定ID的控件左边缘对齐;   
    * android:layout_toRightOf  将该控件的左边缘与给定ID的控件右边缘对齐;     
    * android:layout_alignBaseline  将该控件的baseline与给定ID的baseline对齐;   
    * android:layout_alignTop        将该控件的顶部边缘与给定ID的顶部边缘对齐;   
    * android:layout_alignBottom   将该控件的底部边缘与给定ID的底部边缘对齐;   
    * android:layout_alignLeft        将该控件的左边缘与给定ID的左边缘对齐;   
    * android:layout_alignRight      将该控件的右边缘与给定ID的右边缘对齐; 
  * 居中  
    * android:layout_centerHorizontal 如果为true,将该控件的置于水平居中;   
    * android:layout_centerVertical     如果为true,将该控件的置于垂直居中;   
    * android:layout_centerInParent   如果为true,将该控件的置于父控件的中央;   
  * 指定移动像素  
    * android:layout_marginTop      上偏移的值;  
    * android:layout_marginBottom 下偏移的值;   
    * android:layout_marginLeft 　　左偏移的值;   
    * android:layout_marginRight 　 右偏移的值; 

3.绝对布局：

* 表格布局(TableLayout)是以表格的形式排列控件的，通过行和列将界面划分为多个单元格，每个单元格都可以添加控件。表格布局需要个TableRow配合使用，每一行都由TableRow对象组成，因此tablerow决定表格的行数。
* 布局属性
  * android:stretchColumns——设置该列被拉伸，列号从0开始。例如android：stretchColumns=“0”表示第1列被拉伸
  * android:shrinkColumns——设置该列被收缩，列号从0开始。例如android：shrinkColumns=“0”表示第1列被拉伸
  * android:collapseColumns——设置该列被隐藏，列号从0开始。例如android：collapseColumns=“0”表示第1列被拉伸
* 控件属性
  * android:layout_column——设置该单元格显示位置，如android:layout_column=“1” 表示在第2个位置显示
  * android:layout_span——表示该单元格占据几行，默认为一行

## 二、布局实现

#### 线性布局：

```xml
<?xml version="1.0" encoding="utf-8"?>
<android.support.constraint.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
xmlns:app="http://schemas.android.com/apk/res-auto"
xmlns:tools="http://schemas.android.com/tools"
android:layout_width="match_parent"
android:layout_height="match_parent"
tools:context=".Main3Activity">

<LinearLayout
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical">


    <LinearLayout
        android:id="@+id/line1"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="horizontal"
        android:layout_marginLeft="10dp"
        android:layout_marginRight="10dp">
        <Button
            android:textSize="10dp"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="one,one">
        </Button>
        <Button
            android:textSize="10dp"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="one,two">
        </Button>
        <Button
            android:textSize="10dp"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="one,three">
        </Button>
        <Button
            android:textSize="10dp"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="one,four">
        </Button>
    </LinearLayout>
    <LinearLayout
        android:id="@+id/line2"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="horizontal"
        android:layout_marginLeft="10dp"
        android:layout_marginRight="10dp">
        <Button
            android:textSize="10dp"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="two,one">
        </Button>
        <Button
            android:textSize="10dp"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="two,two">
        </Button>
        <Button
            android:textSize="10dp"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="two,three">
        </Button>
        <Button
            android:textSize="10dp"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="two,four">
        </Button>
    </LinearLayout>
    <LinearLayout
        android:id="@+id/line3"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="horizontal"
        android:layout_marginLeft="10dp"
        android:layout_marginRight="10dp">
        <Button
            android:textSize="10dp"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="three,one">
        </Button>
        <Button
            android:textSize="10dp"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="three,two">
        </Button>
        <Button
            android:textSize="10dp"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="three,three">
        </Button>
        <Button
            android:textSize="10dp"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="three,four">
        </Button>
    </LinearLayout>
    <LinearLayout
        android:id="@+id/line4"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="horizontal"
        android:layout_marginLeft="10dp"
        android:layout_marginRight="10dp">
        <Button
            android:textSize="10dp"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="four,one">
        </Button>
        <Button
            android:textSize="10dp"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="four,two">
        </Button>
        <Button
            android:textSize="10dp"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="four,three">
        </Button>
        <Button
            android:textSize="10dp"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="four,four">
        </Button>
    </LinearLayout>
</LinearLayout>
</android.support.constraint.ConstraintLayout>
```

#### 相对布局

```
<?xml version="1.0" encoding="utf-8"?>
<android.support.constraint.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".Main1Activity">

    <RelativeLayout
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:orientation="horizontal"
        android:background="#000000">

        <Button
            android:id="@+id/RED"
            android:layout_width="80dp"
            android:layout_height="80dp"
            android:background="@android:color/holo_red_dark"
            android:text="RED"/>
        <Button
            android:id="@+id/ORANGE"
            android:layout_width="80dp"
            android:layout_height="80dp"
            android:layout_centerHorizontal="true"
            android:background="@android:color/holo_orange_dark"
            android:text="ORANGE"/>
        <Button
            android:id="@+id/YELLOW"
            android:layout_width="80dp"
            android:layout_height="80dp"
            android:layout_alignParentRight="true"
            android:background="@android:color/holo_orange_light"
            android:text="YELLOW"/>
        <Button
            android:id="@+id/BLUE"
            android:layout_width="80dp"
            android:layout_height="80dp"
            android:layout_centerInParent="true"
            android:background="@android:color/holo_blue_bright"
            android:text="BLUE"/>
        <Button
            android:id="@+id/GREEN"
            android:layout_width="80dp"
            android:layout_height="80dp"
            android:layout_toLeftOf="@+id/BLUE"
            android:layout_centerVertical="true"
            android:background="@android:color/holo_green_light"
            android:layout_marginRight="10dp"
            android:text="GREEN"/>
        <Button
            android:id="@+id/INDIGO"
            android:layout_width="80dp"
            android:layout_height="80dp"
            android:layout_toRightOf="@+id/BLUE"
            android:layout_centerVertical="true"
            android:background="@android:color/holo_purple"
            android:layout_marginLeft="10dp"
            android:text="INDIGO"/>
        <Button
            android:id="@+id/VIOLET"
            android:layout_width="match_parent"
            android:layout_height="80dp"
            android:layout_alignParentBottom="true"
            android:background="@android:color/holo_red_light"
            android:text="VIOLET"/>

    </RelativeLayout>




</android.support.constraint.ConstraintLayout

```

#### 绝对布局

```
<?xml version="1.0" encoding="utf-8"?>
<android.support.constraint.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".Main2Activity">
    <TableLayout
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:stretchColumns="1"
        android:background="#000000">



        <TableRow>
            <Button
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_column="0"
                android:background="@android:color/black"
                android:textColor="@android:color/white"
                android:text="Open..."/>
            <Button
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_column="2"
                android:background="@android:color/black"
                android:textColor="@android:color/white"
                android:text="Ctrl-O"/>
        </TableRow>
        <TableRow>
            <Button
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_column="0"
                android:background="@android:color/black"
                android:textColor="@android:color/white"
                android:text="Save..."/>
            <Button
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_column="2"
                android:background="@android:color/black"
                android:textColor="@android:color/white"
                android:text="Ctrl-S"/>
        </TableRow>
        <TableRow>
            <Button
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_column="0"
                android:background="@android:color/black"
                android:textColor="@android:color/white"
                android:text="Save as..."/>
            <Button
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_column="2"
                android:background="@android:color/black"
                android:textColor="@android:color/white"
                android:text="Ctrl-Shift-S"/>
        </TableRow>
       <View
           android:layout_width="match_parent"
           android:layout_height="3dp"
           android:background="@android:color/white">

       </View>
        <TableRow>
            <Button
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_column="0"
                android:background="@android:color/black"
                android:textColor="@android:color/white"
                android:text="X Import..."/>

        </TableRow>
        <TableRow>
            <Button
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_column="0"
                android:background="@android:color/black"
                android:textColor="@android:color/white"
                android:text="X Export..."/>
            <Button
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_column="2"
                android:background="@android:color/black"
                android:textColor="@android:color/white"
                android:text="Ctrl-E"/>
        </TableRow>
        <View
            android:layout_width="match_parent"
            android:layout_height="3dp"
            android:background="@android:color/white">

        </View>
        <TableRow>
            <Button
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_column="0"
                android:background="@android:color/black"
                android:textColor="@android:color/white"
                android:text="Quit"/>

        </TableRow>
    </TableLayout>
</android.support.constraint.ConstraintLayout>
```

## 三、实验结果图：

![](http://m.qpic.cn/psb?/V12e5dyR1bzWxY/hpN.PX*679pEWHXQKIOWp8F4bpWx7mMrN3Of5H5Dvc8!/b/dL4AAAAAAAAA&bo=zwFbAwAAAAADF6Q!&rf=viewer_4)

![](http://m.qpic.cn/psb?/V12e5dyR1bzWxY/bITmkLYrBrsHWjPmMHyts0UcgsGLXwiV4Ak5ehYaBR4!/b/dLkAAAAAAAAA&bo=zwFbAwAAAAADF6Q!&rf=viewer_4)

![](http://m.qpic.cn/psb?/V12e5dyR1bzWxY/t7d2wZUXtIZ0ZCZhnNRe*kIw.dfK9Jm7DcSjdzldTu0!/b/dL8AAAAAAAAA&bo=zwFbAwAAAAADF6Q!&rf=viewer_4)

![](http://m.qpic.cn/psb?/V12e5dyR1bzWxY/t2wh0.mnpdvRUNAuLmvXNdjkJUoC.EE4YAPUe0p2nAU!/b/dMMAAAAAAAAA&bo=zwFbAwAAAAADF6Q!&rf=viewer_4)