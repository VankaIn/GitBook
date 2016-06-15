;# Strategy - 策略模式

###场景1.小明上班踩单车，以每小时 20km 的速度前进


* 程序设计一：

  ```
  class People(){
    public void goWork(){
      println("每秒20km/h前进");
    }
  }
  ```
  ```
  main {
    People xiaomi = new People();
    xiaomi.goWork(); 
  }
  ```

---

###场景2.小明有钱了，买了台汽车，现在上班速度为60km/s 了




> 明显以上程序无法实现，所以要进一步扩展



* 程序设计二：


```
//peopel 类
class People(){
  public String gongJu;

  public People(String gongju){
    this.gognju = gongju;
  }  
  
  public void setGongJu(String gongju){
    this.gongju = gongju
  }

  //peopel 上班的方法
  public void goWork(){
    if(gongju == "danche"){
      println("每秒20km/h前进");
    } else if(gongju == "qiche"){
      println("每秒60km/h前进");
    }
  }
}
```

```
//主方法
main {
  People xiaomi = new People("qiche");
  xiaomi.goWork(); 
  
  //换单车？
  xiaomi.setGongJu("danche");
  xiaomi.goWork;
}
```


> 但是上面的用字符串表示不好，例如<br>
> 1.People xiaomi = new People("qichi");这样一时打错了，程序就没输出了，小明就没去上班了，哈哈哈<br>
> 2.如果小明现在开飞机上班呢？ 那不是要改小明的类吗？这样违背了<开放扩展，封闭修改>的设计原则啊<br>
> 所以优化一下。于是我们用一个类来代替代表交通工具，而不是 String。



---


*程序设计3
```
//交通工具类
class JiaoTongGongJu{
  int sudu;
  
  public JiaoTongGongJu(int sudu){
    this.sudu = sudu;
  } 
  
  public void go(){
    print（"每秒 sudu km/h前进"）；
  };
}
```
```
//peopel 类
class People(){
  public JiaoTongGongJu gongJu;

  public People(JiaoTongGongJu gongju){
    this.gognju = gongju;
  }    
  
  public void setGongJu(JiaoTongGongJu gongju){
    this.gongju = gongju;
  }
  
  //peopel 上班的方法
  public void goWork(){
      gongju.go();
  }
}
```

```
main {
  JiaoTongGongJu qiche = new JiaoTongGongJu(60);
  People xiaomi = new People(qiche);
  xiaomi.goWork(); 
  
  //以后想换单车？
  JiaoTongGongJu danche = new JiaoTongGongJu(40);
  xiaomi.setGongJu(danche);
  xiaomi.goWork(); 
}
```