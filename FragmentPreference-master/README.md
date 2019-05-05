# FragmentPreference
Using Preferece Fragment to Realize Settings Page
## 使用PrefereceFragment实现设置页面
## 一、PreferenceFragment的布局文件
## preference.xml代码：
```xml
<?xml version="1.0" encoding="utf-8"?>
<PreferenceScreen xmlns:android="http://schemas.android.com/apk/res/android">
    <PreferenceCategory android:title="In-line preferences">
       <CheckBoxPreference
           android:key="checkbox preference"
            android:title="Checkbox preference"
           android:summary="This a checkbox" />
    </PreferenceCategory>
   <PreferenceCategory android:title="Dialog-based preferences">
        <EditTextPreference
           android:key="edit text preference"
           android:title="Edit Text Preference"
           android:summary="An example that uses an edit text dialog"
            android:dialogTitle="Enter your favorite animal" />
        <ListPreference
            android:key="list preference"
            android:title="List preference"
            android:summary="An example that uses a list dialog"
            android:dialogTitle="Choose one"
            android:entries="@array/example"
            android:entryValues="@array/example" />
    </PreferenceCategory>
    <PreferenceCategory android:title="Launch preferences">
        <PreferenceScreen
            android:key="screen preference"
           android:title="Screen preference"
            android:summary="Shows another screen of preferences">
            <CheckBoxPreference
                android:key="next screen checkbox preference"
                android:title="Toggle preference"
                android:summary="Preference that is on the next screen but same hierarchy" />
        </PreferenceScreen>
        <PreferenceScreen
           android:title="Intent preference"
           android:summary="Launches an Activity from an Intent ">
            <intent
                android:action="android.intent.action.VIEW"
                android:data="http://www.baidu.com"/>>
       </PreferenceScreen>
    </PreferenceCategory>
    <!--设置项关联，选中父选项时，子选项才显示。使用dependency属性-->
    <PreferenceCategory android:title="Preference attributes">
        <CheckBoxPreference
            android:key="parent checkbox preference"
            android:title="Parent checkbox preference"
            android:summary="This is visually a parent" />
        <!-- 子类的可见类型是由样式属性定义的 -->
        <CheckBoxPreference
            android:dependency="parent checkbox preference"
            android:key="child checkbox preference"
            android:title="Child checkbox preference"
            android:summary="This is visually a child" />
    </PreferenceCategory>
</PreferenceScreen>    
```
## 二、创建PreFragment,并将布局文件加载进去
## PreFragment.java代码：
```java
public class PreFragment extends PreferenceFragment {
    @Override
    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        //从xml文件中加载选项
        addPreferencesFromResource(R.xml.preference);
    }
}
```
## 三、主活动设置(MainActivity)
## MainActivity.java代码：
```java
public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        //加载Fragment
        FragmentManager fragmentManager=getFragmentManager();
        //开启一个新事务
        FragmentTransaction transaction=fragmentManager.beginTransaction();
        PreFragment preFragment=new PreFragment();
        transaction.add(R.id.main,preFragment);
        transaction.commit();
    }
}
```
## 结果截图如下：
![](http://m.qpic.cn/psb?/V11yBUmB1rpVYD/zBZLNlwIIlRvcMJpJAPEGM9S5XgDmYkdNUrd9H93v.M!/b/dL8AAAAAAAAA&bo=0wE0AwAAAAADB8c!&rf=viewer_4)

![](http://m.qpic.cn/psb?/V11yBUmB1rpVYD/IawDrhfeaOBTRJ4XoQXNfboMfaPjokH.a3sqzT*tK*M!/b/dE8BAAAAAAAA&bo=0wE0AwAAAAADF9c!&rf=viewer_4)

![](http://m.qpic.cn/psb?/V11yBUmB1rpVYD/nglc8fl4rEwM3J6ANVZ32nX.9tG3z0vhNmoA86DEnFE!/b/dAgBAAAAAAAA&bo=0wE0AwAAAAADB8c!&rf=viewer_4)