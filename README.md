# 学习java

# 2020.6.8
      数据类型容量：  byte 、char 、short  ---> int ---> long ---> float ---> double
                  当byte 、char 、short三种类型互相做运算时，结果需要至少int型
# 2020.6.9
      String 类型定义变量必须是双引号 String name = "lmz"  ; Char类型定义变量必须是单引号 Char x = 'L'
      二进制 0，1                  例子： 01   (最大数<2)
      八进制 0-7  以0开头          例子： 0123 (最大数<8）
      十进制 0-9                   例子： 123
      十六进制 0-9及A-F  以0x开头  例子： 满16进1 --> 0x21AF + 1 = 0X21B0
      二进制转换为十进制的简便算法  00001110 -->   1*2^3 + 1*2^2 + 1*2^1 + 0*2^0 = 14 （符号位不参与运算）
      十进制转换为二进制的算法(除2取余数然后逆序) 
                      例子：  13/2-->商6余1-->6/2-->商3余0-->3/2-->商1余1--->1/2-->商0余1-->0/2-->商0余0--》···
                                        1              0                1            1              0       ··
                                然后逆序    00001101        
      二进制数又分为正数和负数 ，区分的方式就是符号位是0还是1  0就表示正数 1就表示负数（这里的符号位是指从右往左数的第8位）
      二进制正数如何转换为负数：
               例子:                    0 0 0 0 1 1 1 0        （14）
               第一步: 符号位变为1       1 0 0 0 1 1 1 0        (称为 -14的原码）
               第二步：除符号位外取反    1 1 1 1 0 0 0 1        （称为-14的反码）
               第三步：反码加 1          1 1 1 1 0 0 1 0        （称为-14的补码）
                得出的补码即为某整二进制数的对应负数
# 2020.6.10
      位运算符  <<左移  >>右移
         计算方法   21 << 2 ，表示21左移2位，此时的数变为了 21 * 2^2   -->84
# 2020.6.11
       程序流程控制：：顺序机构、分支结构、循环结构
       当有多个if else 且没有大括号括起来   if和else默认就近原则
       math.random() : 介于 0（包含） ~ 1（不包含） 之间的一个随机数 
       获取一个随机数
                [a,b)       math.random() * (b-a) + a
                [a,b]       math.random() * (b-a+1) + a
# 2020.6.12
    for循环的真实执行顺序
      :     int num =1;
            for(system.out.print('a);   num<=3;    system.out.print('c'),num++){
                   // 语句1              语句2                语句3
                  system.out.print('b')   //语句4
            }
            输出： a b c b c b c  （语句1-->语句2--(满足条件)语句4 -->语句3 -->语句2 ······）
# 2020.6.17
     数组一经定义，长度不可再变
# 2020.6.29
     学习了二维数组的一些属性
         1.  int[][] arr = new int[3][2]
             system.out.println(arr[1])  //是一个地址值（因为都是堆栈存储 ，栈内存储地址值）
             system.out.println(arr[1][1])  //0    此处的值根据声明数组的类型决定  new float：0.0   new boolean:false  new string:null 
         2.  int [][] arr = new int[3][]
             system.out.println(arr[1])  // null
             system.out.println(arr[1][1]) //报错了
         3. int[] x  ===  int x[] 
            int[][] y ===  int[] y[]  === int y[][]          
     
# 2020.7.3
     属性（局部变量）因为有默认隐式赋值，就不需要显式赋值了
     局部变量必须要显式赋值
# 2020.7.9
      方法的重载： 在同一个类中，允许出现一个以上同名的方法，只要它们的参数个数或者参数类型不同即可。
# 2020.7.10
      方法的形参的传递机制是什么：值传递机制
            如果方法的参数传递的是基本数据类型，那么实参赋值给形参的是真实的数据值
            如果方法的参数传递的是引用数据类型，那么实参赋值给形参的是数据的地址值
# 2020.7.14
     String s1 = "hello"  
         : s1是一个引用数据类型而不是基本数据类型，这里说明String是一个比较特殊的类
# 2020.7.15
      面向对象的三大特性：  继承 封装 多态
      封装性的体现之一  ：  类的属性设置private私有化，对外暴露可以获取(get)和设置(set)私有属性的public方法
      java规定的四种权限（从小到大）：  private  缺省  protected   public
      修饰类的权限修饰符只能用缺省或者public,而类中的内部结构可以由4种修饰符任意一个修饰
      类的成员： 属性 方法 构造器(构造方法，每一个类都有构造器)
      构造器的作用：  
            Person p = new Person();   
            Person()就是一个构造器   作用  1.创建一个对象  2.给对象进行初始化赋值
# 2020.7.20
     默认构造器的权限取决于定义类时的权限修饰符
# 2020.7.27
     for(;;){
         //不加条件的for循环，则一直处于循环状态
         if(true){
             break  //只有break可以退出该循环
         }else{
            return ;   //return是退出当次循环
         }
        
     }
# 2020.7.29
    继承性的一些特征
           ： 子类A继承父类B后，子类A中就获取了父类B中声明的所有的属性和方法。父类中一些private的属性或方法，子类仍然获取得到，只是因为封装
       性的影响，使得子类不能直接调用父类的结构而已
    方法的重写ovveride/overwrite?
           :   1. 子类重写的方法的权限修饰符不小于父类被重写的方法的权限修饰符
               2. 子类不能重写父类中使用private权限修饰符声明的方法
# 2020.7.31
     super关键字相关
         ： 在构造器中使用this(形参列表)，表示调用本类中符合形参列表格式的构造器；
                    而使用super(形参列表)，表示调用父类符合形参列表格式的构造器；
            this(name) 和 super(name)要求都必须写在第一行，所以二者不可同时出现
            如果类中的构造器没有显示的使用this(形参列表）或者super(形参列表）,则默认调用了父类中空参的构造器即super();
     多态？
           ：对象的多态性---父类的引用指向子类的对象
              Person p1 = new Man();
              在程序编译期，p1只能执行父类中声明过的方法，但在程序执行时，p1调用的却是子类中重写的方法
     多态性的使用前提？
              ：1. 类的继承关系
                2.  方法的重写
# 2020.8.3
      多态性的使用举例
              ： public void test(Animal anima){
                     animal.eat();
                     animal.shout();
                 }
                当dog类调用test方法是，输出 狗：进食 汪汪汪！
                当cat类调用test方法时，输出 猫：进食 喵喵喵！
                这是多态的一个作用，若没有多态性，那么此方法的参数必须是Animal类，而不可以是其子类dog或cat,
                并且dog要去调用dog类上的test方法，cat要去调用cat类上的方法，代码冗杂
        多态性只适用于方法，不适用于属性变量，即变量不存在多态性
# 2020.8.5
        equals()方法？
            ：比较对象的实体内容是否相等
              注意点：若是自己写的类，那么调用equals()方法，是继承自Object类的方法，此时比较的是对象的地址值，类似于==
                      而java封装的类如String Date等，equal()方法是经过重写的，此时比较的才是实体内容
                    所以，若是自定义的类需要使用equal()的话，就需要在类中重写，默认提供了一键重写
# 2020.8.6
      java中两个字符串的比较
        ：   String s1 = 'AA';
             String s1 = 'AA';
             system.out.println(s1 == s2) ;  //true  虽然String是引用类型，但是这样声明的字符串还是相等的

             s1 = 'BB'
             system.out.print(s2) //'AA'
      当syso一个对象实例的时候，其实是syso对象实例.toString()
      如何创建一个单元测试？
           详细步骤：    1. 选中当前工程 --右键选择 build path -- add libraries -- Junit 4 -- 下一步
                         2. 创建类（public 无参构造器）
                         3. 创建单元测试方法 （public 、 void 、无参）
                         4. 在方法前声明注解 ： @Test   (需import相关包）
                         5. 测试时 -- 双击方法名，右键选择 Run as -Junit test
           简单步骤：    在需要单元测试的地方(需要保证类的条件)，直接写上@Test 并且写上测试方法，此时会有错误，点击需要的操
                      作，系统自己会执行一系列步骤
     基本数据类型与包装类之间的相互转换
           ： 1. 基本数据类型-->包装类  ：  用 new + 类(某个值)    如：int num1 = 2 ; Interge obj1 = new Interge(num1)
              2. 包装类 ---> 基本数据类型  ： 用obj1.xxxValue()    如：int num2 = obj1.intValue()
              自动拆箱与自动装箱可以简化以上过程   如 ： int num3 = obj1 实际就等于 int num3 = obj1.intValue()
              3.String与二者的相互转换    String s = "123"
                  String --> 基本类型或包装类   
                      类.parseXxx()   如：int i = Interge.parseInt(s)
                  基本类型 -->  String
                     String.valueof()   如： String s1 = String.valueof(i)
# 2020.8.7
        satic声明的属性或方法是所有实例可以共享的，非static声明的变量称为实例变量，
         静态方法（static声明的方法）内部只能使用静态方法或静态属性，不可以使用非静态方法或属性；非静态方法可以随便调用  
         静态方法不能使用this关键字
         this()表示本类中的无参构造器，super代表父类的无参构造器
         单例模式：
               对某个类来说只存在一个对象实例
         静态属性、静态方法、静/非静态代码块之间的关系？
              ： 静态属性、静态方法随着类的加载而加载 ，静态代码块会随着类的加载而执行，非静态代码块随着对象的创建而执行
                 静态代码块内部只能调用静态属性或方法，非静态代码块可以随意调用
# 2020.8.10
       静态代码块、非静态代码块、构造器之间的执行顺序？
              ：由父及子，静态先行
           注意：由于main方法也是类中的一个静态方法，要想执行它，肯定是先加载好类，所以非静态代码块也在main方法前执行
       final关键字的作用？
             ：1. 当final修饰一个类时，表示这个类不能再被其他类继承了
               2. 当final修饰一个方法时，表示这个方法不能再被重写了
               3.当final修饰一个变量时，表示这个变量不能再被二次赋值了
             
# 2020.8.11
         抽象类的说明
             ：abstract修饰类 ->抽象类（不能再new实例了）
              abstract修饰方法 ->抽象方法
              包含抽象方法的类一定是一个抽象类，因为抽象方法不可以被调用，怎么让它不被调用呢，就是让类不可以造对象
          举一个抽象类及抽象方法的运用场景
              ：    首先声明一个代表几何图形的类，然后声明一个方法求其面积，因为不知道这个几何图形到底是什么图形，那么没有固定求面积的公式，
                 那这时怎么声明此方法呢，就是用abstract抽象声明该方法，当创建一个三角形继承自该几何图形类时，到了具体的图形，求面积方法就
                 可以固定了，那么在三角形类中重写求面积的方法即可
          abstract关键字使用的注意点？
              :abstract不能用来修饰哪些地方
                   1.私有方法
                       因为既然一个方法用abstract修饰，那表明在子类中是需要重写的，这时若此方法还使用private修饰，那么
                       子类获取不到，又何来重写一说
                   2. 静态方法
                       因为static声明的方法，就算子父类中同名同参，那么也不叫重写，所以不能共同使用
                   3. final方法
                       final方法不能重写，同1
                   4. final的类
                       final的类都不能继承，如果还用abstract修饰的话，自身又不能new对象，那搞它干嘛
# 2020.8.12
       如何创建一个匿名子类的实例对象？
              //匿名类肯定是子类
             Person p = new Person(){
                 //方法体里需要重写父类(Person)中的抽象方法
             }
# 2020.8.13
       interface关键字？
             ：用来描述一类事物拥有共同的行为特征
                  >例如：鸟 飞机 子弹   共同特征：会飞
               在JDK7之前：只能声明全局常量及抽象方法
                  ：1. public static final int NUM = 1  因为在interface中写法是固定的，所以默认可以省略 public static final这三个修饰符
                    2. public abstract void fly()       因为在interface中写法是固定的，所以默认可以省略public abstract这两个修饰符
               在JDK8之后：不仅可以声明全局变量、抽象方法，还可以声明静态方法、默认方法
     如何实现接口？（使用implements关键字）
            ：通过实现接口，可以使对应的类拥有接口的行为特征
             class plane implements 接口名称{ 
                //重写对应的抽象方法，否则此类也必须声明为抽象类  
             }
     java类具有单继承性，但是接口却可以同时implements多个，用逗号隔开,并且类可以同时extends和implements
         > class A extends b implements C,D,E
      接口之间也可以使用extends继承，并且支持多继承，即一个接口继承自多个接口
# 2020.8.14
       工厂(xxxFactory)?
             :创建与调用分开写
        如何调用接口中的默认方法？
             ：接口名.super.方法名()
        static的使用限制？
              ：static只能修饰类的内部成员，担当类是一个内部类时，就也可以被static修饰了
        如何实例化内部类的对象？
              外部类Person  内部类Dog/Bird
             ：1. 静态内部类 
                   Person.Dog dog = new Person.Dog()
               2. 非静态内部类
                  Person p = new Person()
                  Person.Bird bird = p.new Bird();
        开发中可能应用到内部类的地方？
              ：在一个方法中返回一个实现了某个接口的类的对象，为了返回这个对象，需要实现一个内部类
# 2020.8.18
       异常处理throws和throw
            ：throws是系统自己监测到异常然后抛给上层处理 ； throw new ... 是手动抛出异常
# 2020.8.25
     IDEA快捷键？
         psvm+回车 ： main方法
         sout+回车  ： syso输出语句
# 2020.8.26
       并行：多个人同时做不同的事
       并发：多个人同时做同一件事，比如：秒杀活动
       如何创建一个线程？
            ：1.声明一个Thread的子类
              2. 子类中重写run方法，执行线程需要执行的逻辑
              3. 在另一个类的main方法中创建该子类对象
              4. 子类对象调用start方法
       线程优先级高低有什么影响？
            ：高优先级的线程要抢占低优先级线程cpu的执行权，但是知识从概率上讲，高优先级的线程高概率的情况下被执行，并不意味着只有高优先级的线程
              执行完以后，优先级低的线程才执行
# 2020.8.27
     创建多线程的第二种方式？
            ：1.声明一个类实现Runnable的接口
              2.重写接口的run方法
              3.在main方法中，创建这个类的实例
              4.将这个实例作为参数传进new Thread( m )的构造器中返回的就是一个线程
                 即   Thread t1 = new Thread(m)
              5. t1调用start()
              注意：此方法要创建多个线程时不需要创建多个实现类的实例，只需多次调用那一个就行
      线程的生命周期？
             ： 新建   -->    就绪    <-->  运行   -->   死亡
                                            |
                                           阻塞
# 2020.8.31
       解决多线程安全的方法？
            1. 同步代码块
                synchronized(同步监听器){ //同步监听器俗称：锁 ，这个地方可以用任何类的实例，因为它就代表一个锁，注意保证所有的线程共用同一把锁
                   //需要同步的代码,不要包多了，也不要包少了
                }
            2.同步方法
               就是将所有需要同步的代码放在一个方法体内，并将该函数属性设置为synchronized。
               此处可以省略同步监视器
                   当同步方法为静态static时，监视器默认是类自身，如Person.class
                   当同步方法为非静态时，监视器默认是this
           3. lock锁   --jdk5.0新增
                private ReentrantLock lock = new ReentrantLock();   //构造函数默认传参为false，就是不公平调用线程的意思，即随机，反之亦然
                try{
                       lock.lock()    //上锁
                       //线程需同步代码的放置地
                }finally{
                       lock.unlock()   //解锁，需要手动调用
                }
       死锁？
            ：不同的线程分别占用对方需要的同步资源不放弃，都在等待对方放弃自己需要的同步资源，就形成了线程的死锁
            注意： 一个线程同步执行时synchronized，会占用那个锁即同步监视器，只有那个同步代码执行完后才会释放那个锁
# 2020.9.1
       线程通信之如何让两个线程交替执行？
             wait()   //当前线程执行了此方法后，就会被阻塞，并释放锁，那此时另一个线程就会获取到锁并执行
             notify()   //另一个线程执行时，会唤醒那个被wait阻塞的线程，当线程执行相应代码后，此时又会执行wait()，自己又被堵塞
             注意：这几个方法都必须使用在同步代码块或同步方法中 ，调用者都是谁呢？都是同步监视器，即锁
       创建线程的第三种方式？
              ：回顾下前两种
                     1.  extends Thread
                     2. implements Runnable
                3.implements Callable
                  具体步骤： ① 声明一个实现了Callable的实现类
                             ② 在重写call方法中编写需要线程执行的代码，此处比前两种线程方法多一个功能，就是可以return一个值
                             ③ main方法中创建实现类的对象o
                             ④ 创建FutureTask类的对象M,将对象o作为参数传递到FutureTask的构造器中
                             ⑤ 执行new Thread(M).start()，到此线程已经编写完毕
                             ⑥ 此步骤是可有可无，若你想获取到②步骤中的返回值，那么可以调用M.get()，值就是你想要的
        创建线程的第四种方式？
              ：使用线程池
                步骤：1.main方法中提供指定线程数量的线程池 ExecutorService servive = Executors.newFixedThreadPool(10) :表示10个线程
                      2.执行指定的线程的操作。根据执行的方法()去提供实现Runbale或Callable的接口实现类的对象
                      3.关闭连接池
# 2020.9.3
        Strgin类型？
              ：字面量创建的字符串数据存放在方法区的字符串常量池中
                new创建的字符串数据，是数据在堆空间中开辟控件存储，实例对象存放的是地址值
        string数据拼接？
               ：当str1 = "aa"+"bb" ,str2= "aabb"  ，那么str1 == str2
                 当一个字符串是由一个变量+一个字符串拼接而成时，那么这个字符串相当于是new出来的
             注意： 加了final声明的str不是变量而是常量
        String数据的不可变性？
                ：声明一个字符串，当改变该字符串的值时，之前变量池中存储的数据并没有改变，只是地址值指向了新的数据
        String于char[]之间的转换？
               ： char[] c1 = str.toCharArray();
                  String str2 = new String(new Char[]{'h' ,'e','l','l','o'})
       String与byte[]之间的转换？  //编码和解码
               ： byte[] bytes = str.getBytes();  //参数可以传递不同的字符集进行编码，如（utf-8,gbk)，没有参数使用的默认的
                  String str2 = new String(bytes)
# 2020.9.4
        String的三个包装类？
            1. String   //不可变的字符序列  底层源码默认char[] 数组length为0；
            2.StringBuffer  //可变的字符序列,相关方法都加了synchronized，就说明是多用于保正多线程安全的场景 ，那么自然的它的效率就比较低  默认16
            3.StringBuilder //可变的字符序列，jdk5.0新增，相关方法没有s'ynchronzied，线程不安全，那么自然的它的效率就高， 默认16
       日期事件类？
             1.java.util.Date
             2.java.sql.Date
                util.Date是sql.Date的父类，sql.Date多用于数据库文件；
# 2020.9.7
       StringBuilder类型拼接字符串的方式？
           ：sb.append("字符串")  而不是用+(加号)拼接   
       日期类格式化？
           ：SimpleDateFormat sdf = new SimpleDateFormat("yyyy-MM-dd hh:mm:ss")   // 构造器参数传自己想要的数据格式
       日历类与Date之间的相互转换？
            ：Date date = Calendar.getInstance().getTime() ;    // 日历---> Date
# 2020.9.8
       如何比较对象的大小？
            ：使用comparable或comparator接口的compareTo() ;
               如果是自定义类对象，那么需要重写compareTo() ; 比较this与传入的obj属性大小
               comparable 自然排序 Arrays.sort(arr)  默认调用compareTo                     多用于复用性比较
               comparator 定制排序  Arrays.sort(arr,new Comparator(){ //重写compare() })   多用于临时性比较
# 2020.9.9
       创建枚举类的方式？
            1.自定义枚举类 
              class Season{ ... }
            2.使用enum关键字定义枚举类
              enum Season{ ... }
       如何自定义注解？
            ：1.声明一个Annotation类型的文件
              2. 方法体里写 String value()就行了  //此处可以声明默认值 String value() default "hello"
              3. 使用 @MyAnnotation(value="hello")
       什么叫元注解？
             ：对现有的注解进行解释说明的注解
# 2020.9.10
       已经有数组去存储多个数据了为什么还要有集合这种结构？
           ：  1.数组一旦初始化以后，其长度就确定了，不可修改
               2.数组一旦定义好，其元素的类型也就确定了
# 2020.9.11
       ArrayList和Linkedlist比较？
             ：Arraylist底层使用Object[] 存储   ， LinkedList底层使用双向链表存储，所以对于频繁插入、删除的结构操作应该选择LinkedList；
       重载？
             ：方法名一样，形参列表不一样的方法函数
       List接口与Set接口？
             ：list接口：数据结构是有序、可重复的   ArrayList 、LinkedList 、Vector
               set接口： 数据结构是无序、且不可重复的    HashSet 、 LinkedHashSet 、 TreeSet
       Set接口的无序性？
             ：不等同于随机性，无序性体现是什么呢？就是在创建时，数据不是按照底层数组的索引顺序来添加的
       Set接口的不可重复性是如何实现的？
             :很简单巧妙
                Set接口插入一个值时，保证其不重复并不是遍历之前所有的跟它比较是否相同，而是将该值转换为一个hash值，再根据某个算法，算出该hash值
                应该保存在集合的哪个位置上，此时判断该位置上是否有元素，若没有，那直接插入成功，若有，那就需要对其进行比较了，如果不相同，那就把这个
                新值以链表形式通过指针放在这个位置的下边（新元素位置是“七上八下”，jdk7/jdk8），如果相同，那就插不进去了
# 2020.9.14
       向Set接口实现的集合里边插入对象需要注意什么？
              ：对象所在的类一定要重写hashCode()和equals()
       HashSet与LinkedHashSet区别？
              ：它们存储的数据都是无序性的，但是LinkedHashSet遍历输出时，数据输出的先后顺序是根据用户添加时的顺序，为什么呢，因为Linked，在添加数据的
              同时，每个数据还绑定了两个引用，分别记录此数据的前一个和后一个，对于需要频繁的遍历操作时，优先使用LinkedHashSet
       自然排序和定制排序？
             ：字然排序就是给改变要比较的对象的类，让它implements Comparable接口，然后重写compareTo()
               定制排序是生成一个comparator()的实例，这个实例的类中是重写过compare()的。
       Map和Collection的区别？
             ： Map是双列数据，存储key-value对的数据 
               Collection是单列数据，存储value数据
      HashMap和Hashtable的异同？（这里的t就是小写）
            ： HashMap是Map的实现类；线程不安全，效率高；可以存储null的key或value
               Hashtable是古老的实现类；线程安全，效率低；不可以存储null的key或value
      HashMap的底层实现原理？（jdk7）
             ：Hash map = new HashMap()
               实例化以后，低层创建了一个长度是16的一维数组Entry[] table;
               当某次put操作时，map.put(key1,value1)
               首先，调用key1所在类的hashCode()计算key1的哈希值，此哈希值经过某种算法后，得到在Entry数组中的存放位置
               若该位置上的数据为空，那么key1,value1添加成功
               若该位置上数据已经有了(key2 ,value2),那么就要比较key1和key2的哈希值，
               如果hash值不相等，那么(key1,value1)以链表的形式存入成功
               否则，就要调用key1所在类的equals方法，
               若equals()返回false,那么那么(key1,value1)以链表的形式存入成功。
               若equals()返回true，那么key1-value1不是添加失败，而是value1会替代value2存储在那。
               
               jdk8之后修改了部分底层原理？
               1.在实例化时，不创建数组了，是在第一次put操作时创建，并且类型为Node[]
               2.jdk7底层结构只有：数组+链表
                 jdk*底层结构有：  数组+链表+红黑树  
               注意：当数组中某个索引位置上的元素以链表形式存在的数据的个数 > 8 && 数组的长度 >64时，此索引位置上的所有数据改为红黑树存储                
      HashMap的扩容？
               ：当数组的size大于临界值且元素将要放的位置非空时，就扩容，默认的扩容方式为原来容量的2倍
# 2020.9.21
      数据结构简述？
         ：数据结构分为
                ：1. 真实结构  
                        ：① 线性表之顺序表
                          ② 线性表之链表
                  2. 抽象结构 （抽象结构里的每一种都是基于真是结构的顺序表或链表而来的）
                       ：① 栈
                         ② 队列
                         ③ 树
                         ④ 图
                         ⑤ 其它
# 2020.9.24
       泛型方法？
           ：泛型方法跟泛型类属于哪个类型是没有任何关系的，如泛型类是T ，那么泛型方法可以是E也可以是T 。
             泛型方法是可以被static修饰的，因为泛型方法是声明即被调用时决定其类型的，而不是引用的泛型类的类型
       泛型在继承方面的体现？
           : 类A是类B的父类，但G<A>并不是G<B>的父类，而是并列关系 。 如Person<Object>和Person<String>是并列关系
# 2020.9.28
      字符集编码的理解？
           ：计算机只认识二进制0、1，由0，1演变出ASCII---它是美国专用的，所以为了适应别的语言的需求，进而产生了一系列字符集（GBK,GB2312等），中国默认使用的
           是GBK, 而编程经常使用的utf-8是什么呢，它属于Unicode，Unicode涵盖了全球所有的字符，是多个编码方案的统称
# 2020.10.9
      流的分类？
           1.节点流
           2.缓冲流(处理流)    --作用：提供读取、写入的速度； 原理：内部提供了一个缓冲区
           3.转换流    --作用： 提供字符流与字节流之间的转换
