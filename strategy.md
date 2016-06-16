# Strategy

###场景1.对一组[1,2,6,4,3,2]进行排序，会怎么写？

* 程序设计1

```
public class MainActivity extends Activity{
    TextView tv;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        tv = (TextView) findViewById(R.id.tv_content);
        //数组创建
        Integer a[] = {1,2,6,4,3,2};
        //数组排序
        DataSorter.sort(a);
        //数组输出到界面
        tv.setText(toStringArray(a));
    }


    /**
     * 把数组转成一段字符串输出到界面
     * @param a
     * @return  一段排好序的字符串
     */
    public String toStringArray(Integer[] a) {
        String str = "";
        for(int i=0; i<a.length; i++) {
            str += a[i].toString() + ",";
        }
        return str;
    }
}
```

```
/**
 * Created by liangjunjie on 16/6/16.
 * 排序工具
 */
public class DataSorter {

    public static void sort(int[] a) {
        for(int i=a.length; i>0; i--) {
            for(int j=0; j<i-1; j++) {
                if(a[j] > a[j+1]) {
                    swap(a, j , j+1);
                }
            }
        }
    }

    private static void swap(int[] a, int x, int y) {
        int temp = a[x];
        a[x] = a[y];
        a[y] = temp;
    }

}
```



> 结果<br>
> ![](36647C2C-F803-44FD-9380-AC749638C600.png)




###场景2.加入现在我要排序的不是一组 数字了，是要对一组 猫按照体重来排序。

