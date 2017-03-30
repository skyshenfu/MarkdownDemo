# 一级标题使用的*

## 一级标题使用的**

- 无序列表使用+空格或者-空格 
- blue
- green
  1. 有序列表使用x.空格
  2. Python
  3. Android

![测试图片](https://ss0.bdstatic.com/94oJfD_bAAcT8t7mm9GUKT-xh_/timg?image&quality=100&size=b4000_4000&sec=1490839423&di=0d4301937169d7ddb13c5e9527c38122&src=http://imgsrc.baidu.com/forum/pic/item/241f95cad1c8a786bad0389f6709c93d71cf50ac.jpg)

[sky神父的github](https://github.com/skyshenfu/UIkiller)

> “技术本身并没不可耻”————快播王欣

> > 

*TEST*

___STRONG___

~~张添一~~

---

| A    | B    |      |      |
| ---- | ---- | ---- | ---- |
| 1    | 2    |      |      |
|      |      |      |      |
|      |      |      |      |
|      |      |      |      |
|      |      |      |      |
---



	    import android.content.Context;
	    import android.util.Log;
	    import java.lang.ref.WeakReference;
	
	    import javax.inject.Inject;
	
	    /**
	     * Created by zty
	     * 个人github地址：http://www.github.com/skyshenfu
	     * 日期：2017/3/16
	     * 版本号：1.0.0
	     * 描述：
	     */
	
	        public abstract class BasePresenterImpl<V extends BaseView> implements BasePresenter{
	        protected WeakReference<V> viewRefs;
	        protected WeakReference<Context> contextRefs;
	        @Override
	        public void detachMvpView() {
	            if (viewRefs!=null){
	                viewRefs.clear();
	                Log.e("123", "getView: 回收");
	                viewRefs=null;
	            }
	            if (contextRefs!=null){
	                contextRefs.clear();
	                Log.e("123", "getContextView: 回收");
	                contextRefs=null;
	            }
	        }
	
	        public void attachMvpView(V view,Context context) {
	            viewRefs=new WeakReference<V>(view);
	            contextRefs=new WeakReference<Context>(context);
	        }
	        public V getView(){
	            if (viewRefs!=null){
	                return viewRefs.get();
	            }else {
	                return null;
	            }
	        }
	        public Context getContext(){
	            if (viewRefs!=null){
	                return contextRefs.get();
	            }else {
	                return null;
	            }
	        }
	    }


