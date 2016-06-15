# Strategy - 策略模式

###场景一.小明上班踩单车，以每小时 20km 的速度前进


* 程序设计

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
