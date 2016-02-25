# SwipeListView

[![License](https://img.shields.io/badge/license-Apache%202-green.svg)](https://www.apache.org/licenses/LICENSE-2.0)

##介绍 Introduction##
**SwipeListView** - 自定义Item的ViewGroup，实现在ListView中Item侧滑出菜单的效果。(Customize the ViewGroup that slideslip item to display sliding menu in listview.)

##截图 Screenshot##
![screenshot_gif](https://github.com/yuqirong/SwipeListView/blob/master/screenshots/20151213140251.gif)

##下载 Demo Download##
[Download](https://github.com/yuqirong/SwipeListView/blob/master/screenshots/app-debug-unaligned.apk)

##博客 Blog##
[《让你的ListView更炫酷，实现侧滑删除效果》](http://yuqirong.me/2015/12/13/%E8%AE%A9%E4%BD%A0%E7%9A%84ListView%E6%9B%B4%E7%82%AB%E9%85%B7%EF%BC%8C%E5%AE%9E%E7%8E%B0%E4%BE%A7%E6%BB%91%E5%88%A0%E9%99%A4%E6%95%88%E6%9E%9C/)


##用法 Usage##
###step 1###
把SwipeListView控件作为父布局添加到你的item.xml中，按钮的布局一定要在最底层。(Include the SwipeListView as root ViewGroup widget in your item.xml layout,the menu layout must be in bottom.)

	<?xml version="1.0" encoding="utf-8"?>
	<com.yuqirong.swipelistview.view.SwipeListLayout xmlns:android="http://schemas.android.com/apk/res/android"
	    android:id="@+id/sll_main"
	    android:layout_width="match_parent"
	    android:layout_height="wrap_content" >
	
	    <LinearLayout
	        android:layout_width="wrap_content"
	        android:layout_height="match_parent"
	        android:layout_gravity="center_vertical"
	        android:orientation="horizontal" >
	
	        <TextView
	            android:id="@+id/tv_top"
	            android:layout_width="80dp"
	            android:layout_height="match_parent"
	            android:background="#66ff0000"
	            android:gravity="center"
	            android:text="置顶" />
	
	        <TextView
	            android:id="@+id/tv_delete"
	            android:layout_width="80dp"
	            android:layout_height="match_parent"
	            android:background="#330000ff"
	            android:gravity="center"
	            android:text="删除" />
	    </LinearLayout>
	
	    <LinearLayout
	        android:layout_width="match_parent"
	        android:layout_height="match_parent"
	        android:layout_gravity="center_vertical"
	        android:background="#66ffffff"
	        android:orientation="horizontal" >
	
	        <TextView
	            android:id="@+id/tv_name"
	            android:layout_width="wrap_content"
	            android:layout_height="match_parent"
	            android:gravity="center_vertical"
	            android:padding="15dp"
	            android:text="hello" />
	    </LinearLayout>
	
	</com.yuqirong.swipelistview.view.SwipeListLayout>

PS：如果你的侧滑菜单中的View超过一个，则需要有ViewGroup包裹。像上面一样用LinearLayout来包裹置顶、删除两个View。(If your views in sliding menu than one, you need to have wrapped it by ViewGroup.As above with LinearLayout to wrap top and remove views.)

###step 2###

	class ListAdapter extends BaseAdapter {

		@Override
	    public View getView(final int arg0, View view, ViewGroup arg2) {
	           if (view == null) {
	               view = LayoutInflater.from(mContext).inflate(
	                       R.layout.item, null);
				   ...
	           }
			   ...
		}
	}
	
	@Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
		ListView lv_main = (ListView) findViewById(R.id.listview);
        lv_main.setAdapter(new ListAdapter());
	}

好了，通过上面两步就可以使用SwipeListView，享受吧！(Well, by the above two steps, you can use SwipeListView, enjoy it!)

##联系方式 Contact Me##
新浪微博 Sina Weibo：[@活得好像一条狗](http://weibo.com/yyyuqirong) 

电子邮箱 Email：<yqr271228943@gmail.com>

If you have any questions or want to contact me,you can also leave a message in [Issues](https://github.com/yuqirong/SwipeListView/issues).

##开源许可证 License##

    Copyright (c) 2016 yuqirong 

    Licensed under the Apache License, Version 2.0 (the "License”);
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
