# Strategy

###场景1.对一组[1,2,6,4,3,2]进行排序，会怎么写？

* 程序设计1

```
/**
 * Created by liangjunjie on 16/6/16.
 */
public class MainActivity extends Activity{
    TextView tv;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        tv = (TextView) findViewById(R.id.tv_content);
        int a[] = {1,2,6,4,3,2};
        DataSorter.sort(a);
        tv.setText(toStringArray(a));
    }


    public String toStringArray(int[] a) {
        String str = "";
        for(int i=0; i<a.length; i++) {
            str += a[i] + ",";
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
