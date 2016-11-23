# Lab-8
>本节目标：
>掌握继承，重写和多态的语法

##黄同学升职记
>有一个经理正在给某个张同学布置需求，要求ta在给出的Geometry类基础上，使用继承和多态的语法编写2个类：Rectangle，Circle。同时还需补充Geometry中的>print方法。使得一个数组能够装下这3种类型的对象，同时能调用print方法来进行输出。

###要求
在GitHub下载project，打开inheritance_and_polymorphism，在其中编写代码
####1.	Geometry类几乎已经写好，除了其中的print方法外，不允许修改该类的其他代码。

>a)	编写print方法的要求：

>>i.	调用System.out.println方法来输出toString的返回值

####2.	Circle类需要继承于Geometry类

>a)	只能包含1个字段radius，类型是int。

>b)	实现两个构造器

>>i.	一个是Circle(int radius)

>>ii.	另一个是Circle(String name, String color, int radius)

>c)	重写toString方法

>>i.	要求是在Geometry的toString方法的返回值尾部加上一段描述自己是Circle类，radius的值是多少的字符串。

>>（比如：“No Name is a geometry, whose color is White. And it's a circle with radius 2.” 这个输出中“No Name is a geometry, whose color >>is White.”是Geometry中toString的返回值，需要在后面追加描述自己的信息“And it's a circle with radius 2.”下面的截图也给出了样例）

####3.	Rectangle类需要继承于Geometry类

>a)	只能包含两个字段height和width，类型都是int。

>b)	实现两个构造器

>>i.	一个是Rectangle(int height, int width)

>>ii.	另一个是Rectangle(String name, String color, int height, int width)

>c)	重写toString方法

>>i.	要求是在Geometry的toString方法的返回值尾部加上一段描述自己是Rectangle类，height和width的值是多少的字符串。

>>（比如：“No Name is a geometry, whose color is White. And it's a rectangle with height 12 and width 32.”解>>释同Circle）

>>提示：需要使用super关键字(key word)来调用父类的方法和构造器。

###toString的输出截图
>![alt tag](https://github.com/java-b/Lab-8/blob/master/image.png)
 
>输出第一行是Geometry类的toString结果，第二行是Circle的，第三行是Rectangle的。

###需要编写的类的结构
|类名	|Geometry|
| ------------- |:-------------:|
|父类（superclass）	|Object|
|实例字段	|private String name; private String color;|
|构造器	|Geometry(); Geometry(String name, String color);|
|实例方法	|（需要用到重写的语法）toString();  print();|

|类名	|Rectangle|
| ------------- |:-------------:|
|父类（superclass）|	Geometry|
|实例字段	|private int height; private int width;|
|构造器	|Rectangle(int height, int width); Rectangle(String name, String color, int height, int width);|
|实例方法	|（需要用到重写的语法）toString();  |

|类名	|Circle|
| ------------- |:-------------:|
|父类（superclass）|	Geometry|
|实例字段	|private int radius;|
|构造器	|Circle(int radius); Circle(String name, String color, int radius);|
|实例方法|	（需要用到重写的语法）toString();|  



##测试多态

>根据java的多态语法，继承于Geometry类的Rectangle和Circle类都能解释为Geometry类（即多态）。现在创建一个Geometry类型的数组，将若干Geometry、??>Rectangle、Circle类的实例装入这个数组，使用循环遍历数组中每个元素，并调用print方法，观察各自的输出。

>以上面编写的类为基础，说出下面代码输出的结果。

```
Geometry[] geometries = new Geometry[3];
geometries[0] = new Geometry("Guo Yiming", "Red");
geometries[1] = new Circle("TA Tian", "Black", 5);
geometries[2] = new Rectangle("Zhou Yi", "Yellow", 99, 66);

for (int i = 0; i < geometries.length; i++) {
  // geometries[i].print();如果你成功实现了print方法，你可以直接使用这行代码
  System.out.println(geometries[i]);
}
```
