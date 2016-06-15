# Strategy - 策略模式

###场景1.小明上班踩单车，以每小时 20km 的速度前进


* 程序设计一：

  ```
  class People(){
    public void goWork(){
      println("踩单车 - 每秒20km/h");
    }
  }
  ```
  ```
  main {
    People xiaomi = new People();
    xiaomi.goWork(); 
  }
  ```

###场景2.小明有钱了，买了台汽车，现在上班速度为60km/s 了

 ```
  class People(){
    public String gongJu;
  
    public People(String gongju){
      this.gognju = gongju;
    }
  
    public void goWork(){
      println("踩单车 - 每秒20km/h");
    }
    
    
  }
  ```
  ```
  main {
    People xiaomi = new People();
    xiaomi.goWork(); 
  }
  ```