# [MainPage](../readme.md)/Java  

-
```java
public class VariableDemo{
	public static void main(String[] args){
		
	}
}
```
**calss**:​ 表示定义一个`类`。创建一个类。  

**类**：Java项目最基本的组成单元，一个完整的Java项目有可能会有成千上万个类来组成的。  

class后面跟随的就是这个类的名字，简称：类名。  

类的实现包括两部分：`类的声明`和`类体`。  

**类体**:包括类声明之后的*一对大括号{ }以及它们之间的内容*成为类体，大括号之间的内容称为类体的内容。  

类体分为两部分：`变量的声明`和`方法的定义`。  



```
class 类名{

        变量的声明;

        方法的定义;

    }
```

"VariableDemo"后的大括号表示这个类的范围。  

**public**：表内示程序的访问权限，表示的是任何的场合可以被引用。  

**main**:Java应用程序的入口方法(JVM找到这个程序的入口)，将其声明为public即对外公开，因此JVM便能直接调用它。  
每一个应用程序都必须包含一个main()方法，含有main()方法的类称为主类。  
**static**  
**void**  

## 变量 
  - **变量**分为`成员变量`和`局部变量`  

    - **成员变量**：是变量声明部分声明的变量。（成员变量分为：`实例变量`、`类变量`。用*static*修饰的为类变量（*static变量，也叫静态变量*），否则为实例变量）  

    - **局部变量**：在方法体中声明的变量和方法的参数。  

- **变量的有效范围**
  - `成员变量`在整个类中都有效。
  - `局部变量`只在声明它的方法内有效
  - 方法参数在整个方法内有效。
  - 方法内的局部变量从声明它的位置之后开始有效。  

- **成员变量的隐藏**  
    如果局部变量的名字和成员变量的名字相同，则成员变量被隐藏（即这个成员变量在这个方法内暂时失效）。
  

## 键盘录入
```java
//1.导包，先找到Scanner这个类在哪(idea在进行步骤2后会自动进行导包)
import java.util.Scanner;
public class class1 {
    public static void main(String[] args) {
        //2.创建对象，申明一下，我准备开始用Scanner这个类了。
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入一个数字");
		//3.接收数据
        int i = sc.nextInt();
        System.out.println(i);
    }
}
```
```java
import java.util.Scanner;
```
导包的动作必须出现在类的定义上  
```java
Scanner sc = new Scanner(System.in);
```
此行代码中只有sc为变量名，可变，其余均不可变  
```java
int i = sc.nextInt();
```
其中只有后半为接收数据，前半意为将接收的数据赋值给变量i。此行代码中只有i为变量名，可变，其余均不可变  

## 运算符及表达式  

- **算术运算符**    
对常量或者变量进行操作的符号  

| 运算符 | 说明 |
|-------|------|
| + | 加 |
| - | 减 |
| * | 乘 |
| / | 除 |
| % | 取余数 |  

```java
/*
1.整数相除结果只能得到整除，如果结果想要是小数，必须要有小数参数。
2.小数直接参与运算，得到的结果有可能是不精确的。*/
System.out.println( 10 / 3);//3
System.out.println(10.0 / 3);//3.3333333333333335
```

```java
/*%：取模、取余。
   他做的也是除法运算，只不过获取的是余数而已。*/
System.out.println(10 % 2);//0
System.out.println(10 % 3);//1  
```

- **自增自减运算符**  
自增、自减运算符的作用是使变量的值
增1或减1。  
放在操作元前面的自增、自减运算符，会先将变量的值加1（减1），然后再使该变量参与表达式的运算。  
放在操作元后面的自增、自减运算符，会先使变量参与表达式的运算，然后再将该变量加1（减1）。  
```java
int a = 4;
int b = ++a;//此时b=5，a=5，即a先自增为5再赋值给b
```  

```java
int a = 4;
int b = a++;//此时b=4，a=5，即a先赋值给b再自增为5
```  

**注意**  不管是先++，还是后++。单独写在一行的时候，运算结果是一模一样的。
```java
int a = 4;
++a;
System.out.println(a);
a++;
System.out.println(a);
//以上输出结果均为5
```

- **赋值运算符**  
  - `=` 把等号右边的结果赋值给左边的变量
  - `+=` `-=` `*=` `/=` `%=` 把左边跟右边进行运算，把最终的结果赋值给左边，对右边没有任何影响。  
  
```java
public class example {
  public static void main(String[]args){
    int a = 10;
    int b = 20:
    a += b;//先将a与b相加得到30，再将30赋值给a，对b无影响
    System.out.println(a);//30
    System.out.println(b);//20
  }
}

```  

**注意** 扩展的赋值运算符中隐层还包含了一个强制转换。以下介绍类型转换

- **隐式转换和强制转换**  
  - `隐式转换`也叫自动类型提升。
就是把一个取值范围小的数据或者变量，赋值给另一个取值范围大的变量。此时不需要我们额外写代码单独实现，是程序自动帮我们完成的。  
 
    *规则*  
    - 取值范围小的，和取值范围大的进行运算，小的会先提升为大的，再进行运算。
    - byte、short、char三种类型的数据在运算的时候，都会直接先提升为int，然后再进行运算。
    - byte<short<int< long <float <double  
  - `强制转换`  
    如果要把一个取值范围大的数据或者变量赋值给另一个取值范围小的变量。是不允许直接操作。如果一定要这么干，就需要加入强制转换。  
  
    *书写格式*
    - 目标数据类型 变量名 = （目标数据类型）被强转的数据( 要转成什么类型的，那么就在小括号中写什么类型就可以了。)  

```java
public class example {
    public static void main(String[] args) {
        double a = 12.3;
        int b = (int) a;
        System.out.println(b);//12
    }
}
```  

现在我们回到赋值运算符中隐含的强制转换并给出例子
 
```java
public class OperatorDemo8 {
    public static void main(String[] args) {
        byte a = 10;
        byte b = 20;
        //a += b;
        a = (byte)(a + b);
        System.out.println(a);//30
    }
}
```  
这里的a += b ;实际上相当于 a = (byte)(a + b);  

- **关系运算符（比较运算符）**    

|符号|解释|
|----|----|
| ==   | 就是判断左边跟右边是否相等，如果成立就是true，如果不成立就是false |
| !=   | 就是判断左边跟右边是否不相等，如果成立就是true，如果不成立就是false |
| >    | 就是判断左边是否大于右边，如果成立就是true，如果不成立就是false |
| >=   | 就是判断左边是否大于等于右边，如果成立就是true，如果不成立就是false |
| <    | 就是判断左边是否小于右边，如果成立就是true，如果不成立就是false |
| <=   | 就是判断左边是否小于等于右边，如果成立就是true，如果不成立就是false |  

```java
int a = 10;
int b = 20;
System.out.println( a > b );
```  
```java
int a = 10;
int b = 20;
boolean c = a > b;
System.out.println( c );
```  

- **逻辑运算符**

|符号|解释|
|----|----|
|`&`逻辑与（而且）|两边都为真，结果才是真，只要有一个为假，那么结果就是假。|
|逻辑或（或者） |两边都为假，结果才是假，只要有一个为真，那么结果就是真。|                                        
|`^`异或|如果两边相同，结果为false，如果两边不同，结果为true|
|`!`取反|false取反就是true，true取反就是false|  

- **短路逻辑运算符**   
`&&` `||`  
运算结果与&（|）一致，只不过具有短路效果。即当左边不能确定整个表达式的结果，右边才会执行。如若左边能确定整个表达式的结果，那么右边就不会执行，从而*提高代码的运行效率*。  

- **三元运算符**  
  
  - `格式` 关系表达式？表达式1：表达式2；  
  - `计算规则`   
    计算关系表达式的值。
    如果关系表达式的值为真，那么执行表达式1。
    如果关系表达式的值为假，那么执行表达式2。  

 ```java
 public class OperatorDemo12 {
    public static void main(String[] args) {      
        int a = 10;
        int b = 20;      
       int max =  a > b ? a : b ;//格式：关系表达式 ？ 表达式1 ： 表达式2
        System.out.println(max);
        System.out.println(a > b ? a : b);
    }
}
 ```     

 **注意**  
 此处的表达式1及表达式2不一定为关系表达式里的内容。  

 `举例`  
 ```java
 public class OperatorDemo12 {
   public static void main(String[] args) {      
       int a = 10;
       int b = 20;  
       int c = 30;
       int d = 40;    
      int max =  a > b ? c : d ;
       System.out.println(max);
       System.out.println(a > b ? c : d);
   }

 ```  

 此处a > b 判断为false，输出表达式2，即40（d）  

 ## 计算机底层运行逻辑-原码，反码及补码  

 ### 什么是原码？  
 计算机中一个0或一个1被称为一个bit，8个bit被称为一个字节。  

 `0000 0000`这个就是一个字节，其中第一位为`符号位`，后面七位为`数据`。  

 `符号位`功能是记录该数据正负，`数据`则是具体的数值  

 一个字节最大是`0111 1111`即127，最小是`1111 1111`即-127  

 ### 原码  
 十进制数据的二进制表现形式，最左边是符号位，0为正，1为负。  

 利用原码对正数进行计算不会有问题。  

 ### 原码的弊端  
 **例子**  
 `1000 0000`代表-0，-0同为0  

 此时对0+1正常结果为1，但此处原码进行加1得到的是`1000 0001`显示为-1  

 导致出现这种弊端的原因是由于符号位并不参与计算而导致的。就好比数轴加1本因向数轴正方向走一格，但由于-0其符号位为负数，导致加1变为向数轴负方向走一格，从而得到的结果为-1。  

 为解决这种弊端出现了反码。  

 ### 反码  
 反码如若类比上文提到的数轴就相当于将数轴反过来。  

 其计算规则为：正数的反码不变等同于原码，负数在原码的基础上，符号位不变，数值取反，0变1，1变0。  

 |十进制数|原码|反码|
 |-------|----|----|
 |-1|1000 0001|1111 1110|
 |-2|1000 0010|1111 1101|
 |-3|1000 0011|1111 1100|
 |-4|1000 0100|1111 1011|
 |-5|1000 0101|1111 1010|
 |-6|1000 0110|1111 1001|  

 此时如果将-4 ——`1111 1011` 进行减1，就会得到`1111 1010`即-5，进行加1，就会得到`1111 1100` 即-3。  

 这种情况下计算并无问题，但反码仍有其弊端。  

 例如：  

 -0原码为`1000 0000`,其反码为`1111 1111`  

 +0原码为`0000 0000`,其反码为`0000 0000`  

 此时如果将-0`1111 1111`加1将会得到+0`0000 0000`  

 故当反码中负数进行跨0计算时将会产生1的误差。  

 为解决此种弊端出现了补码。  

 ### 补码  

 补码可看作将反码向下错一位。 

 由于0在反码中有两种表现形式即-0与+0，故在补码中多出了一位`1000 0000`计算机中将其规定为-128，其无原码及反码。因此一个字节的范围为-128~127。    
 
 ==注意==：正数的反码，补码均与原码一致。 


   |十进制数|原码|反码|补码|
 |-------|----|----|----|
 |+0|0000 0000|0000 0000|0000 0000|
 |-0|1000 0000|1111 1111|0000 0000|
 |-1|1000 0001|1111 1110|1111 1111|
 |-2|1000 0010|1111 1101|1111 1110|
 |-3|1000 0011|1111 1100|1111 1101|
 |-4|1000 0100|1111 1011|1111 1100|
 |-5|1000 0101|1111 1010|1111 1011|
 |-6|1000 0110|1111 1001|1111 1010|
 |...|...|...|...|
 |-126|1111 1110|1000 0001|1000 0010|
 |-127|1111 1111|1000 0000|1000 0001|
 |-128|无|无|1000 0000|  

 现在我们对之前的一些知识点进行进一步解释。  

 ### 对隐式转换及强制转换的解释  

 byte类型的10 `1个字节` 0000 1010  

 short类型的10 `2个字节` 0000 0000 0000 1010

 int类型的10 `4个字节` 0000 0000 0000 0000 0000 0000 0000 1010

 long类型的10 `8个字节` 0000 0000 0000 0000 0000 0000 0000 0000 0000 0000 0000 0000 0000 0000 0000 1010  

- **隐式转换**
 ```java
 public class example{
  public static void main(String[]args){
    byte a = 10;//0000 1010
    int b = a;//0000 0000 0000 0000 0000 0000 0000 1010
  }
 }
 ```  

 隐式转换就是在原有字节上补0，补到转换后变量的字节。  

- **强制转换**
```java
 public class example{
  public static void main(String[]args){
    int a = 300;//0000 0000 0000 0000 0000 0001 0010 1100
    byte b = (byte)a;//0010 1100
  }
 }
 ```   

强制转换就是强制去掉原有变量前多余的字节使其变为强制转换的变量的应有的字节，而在强制去除字节时可能去掉其中的数据使其转换后的数据与原有数据不同，这就是强制转换有可能出错的原因。  

## 对于其他运算符的解释  

==&(逻辑与)== 0为false,1为true  
```java
public class example{
  public static void main(String[]args){
    int a = 200;//0000 0000 0000 0000 0000 0000 1100 1000
    int b = 10;//0000 0000 0000 0000 0000 0000 0000 1010
    System.out.println(a & b);
  }
 }
```  

对a & b进行计算(同为true即1才为true)
```
  0000 0000 0000 0000 0000 0000 1100 1000
& 0000 0000 0000 0000 0000 0000 0000 1010
-----------------------------------------
  0000 0000 0000 0000 0000 0000 0000 1000 //8
```

```java
System.out.println(a & b);//故输出结果为8
```  

==|(逻辑或)==  0为false,1为true
```java
public class example{
  public static void main(String[]args){
    int a = 200;//0000 0000 0000 0000 0000 0000 1100 1000
    int b = 10;//0000 0000 0000 0000 0000 0000 0000 1010
    System.out.println(a | b);
  }
 }
```  

对a | b进行计算(只要有true即1就为true)
```
  0000 0000 0000 0000 0000 0000 1100 1000
& 0000 0000 0000 0000 0000 0000 0000 1010
-----------------------------------------
  0000 0000 0000 0000 0000 0000 1100 1010 //202
```

```java
System.out.println(a | b);//故输出结果为202
```   

==<<(左移)== 向左移位，低位补0  

```java
public class example{
  public static void main(String[]args){
    int a = 200;//0000 0000 0000 0000 0000 0000 1100 1000
    System.out.println(a << 2);//左移2位
  }
 }
```   

`00|00 0000 0000 0000 0000 0000 1100 1000 00|`得到800  

左移一次结果乘2

==>>(右移)== 向右移动，高位补0低位或1  

如果是正数则最高位补0，如果是负数则最高位补1。  

右移一次除2  

==>>>(无符号右移)== 向右移动，高位补0  

无论正负数最高位均补0    

## 判断和循环  

### 判断语句：if语句  

**if语句格式1**

```java
格式：
if (关系表达式) {
    语句体;	
}
```

执行流程：

①首先计算关系表达式的值

②如果关系表达式的值为true就执行语句体

③如果关系表达式的值为false就不执行语句体

④继续执行后面的语句内容  

**第一种格式的细节**：

1. 如果我们要对一个布尔类型的变量进行判断，不要写==，直接把变量写在小括号中即可。

2. 如果大括号中的语句体只有一条，那么大括号可以省略不写。如果大括号省略了，那么if只能控制距离他最近的那一条语句。  

**注意**  

```java
int a = 10;
```  
以上代码为两句，首先声明一个变量int为a，再将10赋值给a。所以有时我们无法确定该行代码为几句，为避免出错建议不要省略{}  

**if语句格式2**

```java
格式：
if (关系表达式) {
    语句体1;	
} else {
    语句体2;	
}
```

执行流程：

①首先计算关系表达式的值

②如果关系表达式的值为true就执行语句体1

③如果关系表达式的值为false就执行语句体2

④继续执行后面的语句内容  

**if语句格式3**

```java
格式：
if (关系表达式1) {
    语句体1;	
} else if (关系表达式2) {
    语句体2;	
} 
…
else {
    语句体n+1;
}
```

执行流程：

①首先计算关系表达式1的值

②如果值为true就执行语句体1；如果值为false就计算关系表达式2的值

③如果值为true就执行语句体2；如果值为false就计算关系表达式3的值

④…

⑤如果没有任何关系表达式为true，就执行语句体n+1。  

### switch语句  

**格式**

```java
switch (表达式) {
	case 1:
		语句体1;
		break;
	case 2:
		语句体2;
		break;
	...
	default:
		语句体n+1;
		break;
}
```  
**格式说明**  

- `表达式`(将要匹配的值)取值为byte,short,int,char。JDK5后可以是枚举，JDK7以后可以是字符串。  
- case后面的值只能是字面量，不能是变量。
- case给出的值不允许重复。  

**执行流程：**

- 首先计算出表达式的值 
- 其次，和case依次比较，一旦有对应的值，就会执行相应的语句，在执行的过程中，遇到break就会结 束。 
- 最后，如果所有的case都和表达式的值不匹配，就会执行default语句体部分，然后程序结束掉。   

**switch的扩展知识：**

- default的位置和省略情况

  default可以放在任意位置，也可以省略

- case穿透

  不写break会引发case穿透现象

- switch在JDK12的新特性

```java
int number = 10;
switch (number) {
    case 1 -> System.out.println("一");
    case 2 -> System.out.println("二");
    case 3 -> System.out.println("三");
    default -> System.out.println("其他");
}
```  

`switch和if第三种格式各自的使用场景`

当我们需要对一个范围进行判断的时候，用if的第三种格式

当我们把有限个数据列举出来，选择其中一个执行的时候，用switch语句  

### for循环结构

**for循环格式：**

```java
for (初始化语句;条件判断语句;条件控制语句) {
	循环体语句;
}
```  

**swich和if第三种格式的各自使用场景**  
 
 - `if的第三种格式`一般用于对范围的判断  
 - `switch`把有限个数据一一列举出来，让我们任选其一  

**格式解释：**

- 初始化语句：  用于表示循环开启时的起始状态，简单说就是循环开始的时候什么样
- 条件判断语句：用于表示循环反复执行的条件，简单说就是判断循环是否能一直执行下去
- 循环体语句：  用于表示循环反复执行的内容，简单说就是循环反复执行的事情
- 条件控制语句：用于表示循环执行中每次变化的内容，简单说就是控制循环是否能执行下去

**执行流程：**

①执行初始化语句

②执行条件判断语句，看其结果是true还是false

​             如果是false，循环结束

​             如果是true，继续执行

③执行循环体语句

④执行条件控制语句

⑤回到②继续  

**for循环示例-求和**

- 求1-5之间的数据和   
- 示例代码：  

```java
public class ForTest02 {
    public static void main(String[] args) {
		//求和的最终结果必须保存起来，需要定义一个变量，用于保存求和的结果，初始值为0
		int sum = 0;
		//从1开始到5结束的数据，使用循环结构完成
		for(int i=1; i<=5; i++) {
			//将反复进行的事情写入循环结构内部
             // 此处反复进行的事情是将数据 i 加到用于保存最终求和的变量 sum 中
			sum = sum + i;
			/*
				sum += i;	sum = sum + i;
				第一次：sum = sum + i = 0 + 1 = 1;
				第二次：sum = sum + i = 1 + 2 = 3;
				第三次：sum = sum + i = 3 + 3 = 6;
				第四次：sum = sum + i = 6 + 4 = 10;
				第五次：sum = sum + i = 10 + 5 = 15;
			*/
		}
		//当循环执行完毕时，将最终数据打印出来
		System.out.println("1-5之间的数据和是：" + sum);
    }
}
```

- 要点：
  - 今后遇到的需求中，如果带有求和二字，请立即联想到求和变量
  - 求和变量的定义位置，必须在循环外部，如果在循环内部则计算出的数据将是错误的  

### while循环  

**格式：**  

```java
初始化语句;
while(条件判断语句){
	循环体;
	条件控制语句;
}
```  

`示例`打印5次HelloWorld

```java
int i = 1;
while(i <= 5){
    System.out.println("HelloWorld");
    i++;
}
System.out.println(i);
```  

**for和while的对比**  

`相同点`运行规则一致  

```java
int i =0;
while(i < 4){
  i++
}
System.out.println();
```  

while循环中，控制循环的变量，对于while循环来说不归属其语法结构中，在while循环结束后，该变量还可以继续使用  

for循环中，控制循环的变量，因为归属for循环的语法结构中，在for循环结束后，就不能再次被访问到了  

但是for循环可做以下改写：  

```java
int = 0;
for( ; i < 4;i++>){
  System.out.println();
}
```  

for循环小括号中的初始化语句可以为空将其写在for循环外  

此时for循环中控制环境的变量不归属其语法结构中，在for循环结束后，该变量还可以继续使用  

`不同点`  

- for循环中：知道循环的次数或者循环的范围
- while循环：不知道循环的次数和范围，只知道循环的结束条件  

while循环，是当满足什么条件的时候，才做某种操作。 当条件不满足时，执行完循环体内全部语句后再跳出（而不是立即跳出循环）。 for循环，就是遍历某一对象，通俗说就是根据循环次数限制做多少次重复操作。 while循环，是当满足什么条件的时候，才做某种操作。  

### do...while循环  

格式：

```java
初始化语句;
do{
    循环体;
    条件控制语句;
}while(条件判断语句);
```

特点：

​	先执行，再判断。

### 循环代码示例  

 ### 一、

要求  
- 给出一个整数。  
  若该整数为回文整数，打印true，否则，返回false(回文整数：形如12321)

```java
import java.util.Scanner;

public class class5 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入一个整数");
        int number = sc.nextInt();
        int temp = number;//由于数值number在while循环内已变为0，故定义了一个变量temp以暂存number的数据，并在结尾以此数据对反转的数进行比较
        int sum = 0;//定义一个变量记录反转后的数据
        while(number > 0){//我们对number取余，当对最后一位取完余后必得到0，故我们可以将条件判断句设为number != 0或number > 0,因此循环就会一直重复至对最后一位取完余后再停止
            int ge = number % 10;//对number取余得到number数据的个位数
            number /= 10;//当我们得到一个数的个位数后，如1234得到4后，应再接连得到3，2，1，故在此将数据除10，将数据的最后一位数除去，以得到十位，百位，千位......
            sum = sum * 10 + ge;//进行第一次循环时，得到sum=0 + 个位，第二次得到sum = 个位 * 10 + 十位，如此循环以记录反转的数据

        }
        System.out.println(sum == temp );
    }
}
```  

### 二、  

要求  
- 给出两个正整数，且不超过int的范围，不用乘、除、取余计算第一个数除第二个数的商和余  

```java
import java.util.Scanner;

public class class1 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入第一个整数");
        int num1 = sc.nextInt();
        System.out.println("请输入第二个整数");
        int num2 = sc.nextInt();
        int sum = 0;
        while (num2 <= num1) {
            num1 = num1 - num2;
            sum++;
        }
        System.out.println("商为：" + sum);
        System.out.println("余数为：" + num1);
    }
}
```  

### 三、  

逢7必过小游戏  

```java
public class class6 {
    public static void main(String[] args) {
        for (int i = 1; i <= 100; i++) {
            if(i / 10 % 10 == 7 || i % 10 == 7 || i % 7 == 0){
                System.out.println("过");
                continue;
            }
            System.out.println(i);
        }
    }
}

```  

### 四、  

不调用MATH类进行算数平方根(只保留整数部分）  

```java
import java.util.Scanner;

public class class7 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入一个整数");
        int num = sc.nextInt();
        for (int i = 1; i <= num; i++) {
            if(num == i * i){
                System.out.println(i + "就是" + num + "的算数平方根");
                break;
            } else if (num <= i * i) {
                System.out.println((i-1) + "就是" + num + "的算数平方根的整数部分");
                break;
            }
        }
    }
}

```  

### 无限循环

**概念：**

​	又叫死循环。循环一直停不下来。

**for格式：**

```java
for(;;){
    System.out.println("循环执行一直在打印内容");
}
```

解释：

初始化语句可以空着不写，表示循环之前不定义任何的控制变量。

条件判断语句可以空着不写，如果不写，默认表示true，循环一直进行。

条件控制语句可以空着不写，表示每次循环体执行完毕后，控制变量不做任何变化。

**while格式：**

```java
while(true){
    System.out.println("循环执行一直在打印内容");
}
```

解释：

​	小括号里面就不能省略了，true一定要写出来，否则代码会报错。

**do...while格式：**

```java
do{
    System.out.println("循环执行一直在打印内容");
}while(true);
```

解释：

​	小括号里面就不能省略了，true一定要写出来，否则代码会报错。

**无限循环的注意事项：**

* 最为常用的格式：while
* 无限循环下面不能再写其他代码了，因为永远执行不到。

## 条件控制语句

* break
* continue

### break:

​	不能单独存在的。可以用在switch和循环中，表示结束，跳出的意思。

代码示例：

```java
//1.吃1~5号包子
for (int i = 1; i <= 5; i++) {
    System.out.println("在吃第" + i + "个包子");
    //2.吃完第三个的时候就不吃了
    if(i == 3){
        break;//结束整个循环。
    }
}
```

### continue:

​	不能单独存在的。只能存在于循环当中。

​	表示：跳过本次循环，继续执行下次循环。

代码示例：

```java
//1.吃1~5号包子
for (int i = 1; i <= 5; i++) {
    //2.第3个包子有虫子就跳过，继续吃下面的包子
    if(i == 3){
        //跳过本次循环（本次循环中，下面的代码就不执行了），继续执行下次循环。
        continue;
    }
    System.out.println("在吃第" + i + "个包子");
}
```  

## Random

Random跟Scanner一样，也是Java提前写好的类，我们不需要关心是如何实现的，只要直接使用就可以了。

### 使用步骤：

1. 导包

```java
import java.util.Random;
导包的动作必须出现在类定义的上边。
```

2. 创建对象

```java
Random r = new Random ();
上面这个格式里面，只有r是变量名，可以变，其他的都不允许变。
```

3. 生成随机数

```java
int number = r.nextInt(随机数的范围);
上面这个格式里面，只有number是变量名，可以变，其他的都不允许变。
随机数范围的特点：从0开始，不包含指定值。比如：参数为10，生成的范围[0,10)
```

代码示例：

```java
//1.导包
import java.util.Random;

public class RandomDemo1 {
    public static void main(String[] args) {
        //2.创建对象
        Random r = new Random();
        //3.生成随机数
        int number = r.nextInt(100);//包左不包右，包头不包尾
        //0 ~ 99
        System.out.println(number);

    }
}
```  

## 数组

### 概念：

​	指的是一种容器，可以同来存储同种数据类型的多个值。

​	但是数组容器在存储数据的时候，需要结合隐式转换考虑。

比如：

​	定义了一个int类型的数组。那么boolean。double类型的数据是不能存到这个数组中的，

​	但是byte类型，short类型，int类型的数据是可以存到这个数组里面的。

建议：

​	容器的类，和存储的数据类型保持一致。

举例：

​	整数1 2 3 4 56 就可以使用int类型的数组来存储。

​	小数1.1 1.2 1.3 1.4 就可以使用double类型的数组来存储。

​	字符串"aaa"  "bbb"  "ccc" 就可以使用String类型的数组来存储。

### 数组的定义  

**格式一**

​	数据类型 [] 数组名

比如：int [] array

**格式二**

​	数据类型  数组名 []

比如： int array []  

**详解：**

数据类型：限定了数组以后能存什么类型的数据。

方括号：表示现在定义的是一个数组。

数组名：就是一个名字而已，方便以后使用。  

### 数组的静态初始化

**完整格式：**

​	数据类型[] 数组名 = new 数据类型[]{元素1，元素2，元素3，元素4...};

比如：

​	int[] arr = new int[]{11,22,33};

​	double[] arr = new double[]{1.1,1.2,1.3};

**格式详解：**

​	数据类型：限定了数组以后能存什么类型的数据。

​	方括号：表示现在定义的是一个数组。

​	数组名：其实就是名字而已，方便以后使用，在起名字的时候遵循小驼峰命名法。

​			arr   namesArr

​	new：就是给数组在内存中开辟了一个空间。

​	数据类型：限定了数组以后能存什么类型的数据。

​			  前面和后面的数据类型一定要保持一致。

​			int[] arr = new double[]{11,22,33};//错误写法

​	方括号：表示现在定义的是一个数组。

​	大括号：表示数组里面的元素。元素也就是存入到数组中的数据。

​			多个元素之间，一定要用逗号隔开。

### 注意点：

* 等号前后的数据类型必须保持一致。
* 数组一旦创建之后，长度不能发生变化。

### 简化格式:

​	数据类型[] 数组名 = {元素1，元素2，元素3，元素4...};

比如：

​	int[] array = {1,2,3,4,5};

​	double[] array = {1.1,1.2,1.3};



### 地址值

```java
int[] arr = {1,2,3,4,5};
System.out.println(arr);//[I@6d03e736

double[] arr2 = {1.1,2.2,3.3};
System.out.println(arr2);//[D@568db2f2
```

打印数组的时候，实际出现的是数组的地址值。

数组的地址值：就表示数组在内存中的位置。

以[I@6d03e736为例：

[ ：表示现在打印的是一个数组。

I：表示现在打印的数组是int类型的。

@：仅仅是一个间隔符号而已。

6d03e736：就是数组在内存中真正的地址值。（十六进制的）

但是，我们习惯性会把[I@6d03e736这个整体称之为数组的地址值。  

地址值对于我们来京，作用不大，简单了解。  

### 数组元素访问  

**格式：**

​	数组名[索引];

**作用：**

* 获取数组中对应索引上的值

* 修改数组中对应索引上的值

  一旦修改之后，原来的值就会被覆盖了。

**代码示例：**

```java
public class ArrDemo2 {
    /*

        数组中元素访问的格式：
                数组名[索引];

         作用：
            1.获取指定索引上对应的元素
            2.修改指定索引上对应的元素


    */
    public static void main(String[] args) {
       int[] arr = {1,2,3,4,5};
       //需求1：获取arr数组中，3索引上的值
        int number = arr[3];
        System.out.println(number);
        System.out.println(arr[3]);

       //需求2：将arr数组中，3索引上的值修改为10
            arr[3] = 10;
        System.out.println("修改之后为:" + arr[3]);

    }
}
```

### 索引

​	也叫角标、下标

​	就是数组容器中每一个小格子对应的编号。

**索引的特点：**

* 索引一定是从0开始的。
* 连续不间断。
* 逐个+1增长。

### 数组的遍历

遍历：就是把数组里面所有的内容一个一个全部取出来。

数组的长度：数组名.length;

通用代码：

```java
for(int i = 0; i < arr.length; i++){
    //在循环的过程中，i依次表示数组中的每一个索引
    sout(arr[i]);//就可以把数组里面的每一个元素都获取出来，并打印在控制台上了。
}
```

### 数组的动态初始化

**格式：**

​	数据类型[] 数组名 = new 数据类型[数组的长度];

**举例：**

```java
//1.定义一个数组，存3个人的年龄，年龄未知
int[] agesArr = new int[3];


//2.定义一个数组，存班级10名学生的考试成绩，考试成绩暂时未知，考完才知道。
int[] scoresArr = new int[10];
```

**数组的默认初始化值：**

整数类型：0

小数类型：0.0

布尔类型：false

字符类型：'\u0000'

引用类型：null

### 数组两种初始化方式的区别

静态初始化：int[] arr = {1,2,3,4,5};

动态初始化：int[] arr = new int[3];

静态初始化：手动指定数组的元素，系统会根据元素的个数，计算出数组的长度。

动态初始化：手动指定数组长度，由系统给出默认初始化值。  

**使用场景：**

只明确元素个数，但是不明确具体的数据，推荐使用动态初始化。

已经明确了要操作的所有数据，推荐使用静态初始化。

**举例：**

* 使用数组来存储键盘录入的5个整数。

  int[] arr = new int[5];

* 将全班的学生成绩存入数组中，已知学生成绩为：66,77,88,99,100

  int[] arr = new int[5];

  arr[0] = 66;

  arr[1] = 77;

  ... 虽然可以实现，但是太麻烦了。

  建议使用静态初始化：int[] arr = {66,77,88,99,100};

### 数组常见问题

当访问了数组中不存在的索引，就会引发索引越界异常。

避免：

​	针对于任意一个数组，索引的范围：
   	最小索引：0
   	最大索引：数组的长度 - 1
           		    数组名.length - 1

```java
public class ArrDemo6 {
    public static void main(String[] args) {
       int[] arr = {1,2,3,4,5,5,5,5,5};
        //用索引来访问数组中的元素
        System.out.println(arr[1]);
        System.out.println(arr[10]);//ArrayIndexOutOfBoundsException

    }
}
```

### 数组的示例  

**一、**

需求：求数组中的最大值

代码示例：

```java  
//max的初始化值一定要是数组中的值。
//循环的开始条件如果为0，那么第一次循环的时候是自己跟自己比了一下，对结果没有任何影响，但是效率偏低
//为了提高效率，减少一次循环的次数，循环开始条件可以写1.


//1.定义数组用来存储5个值
int[] arr = {33,5,22,44,55};
//2.定义一个变量max用来存储最大值
//临时认为0索引的数据是最大的
int max = arr[0];
//3.循环获取数组中的每一个元素
//拿着每一个元素跟max进行比较
for (int i = 1; i < arr.length; i++) {
    //i 索引  arr[i] 元素
    if(arr[i] > max){
        max = arr[i];
    }
}
//4.当循环结束之后，max记录的就是数组中的最大值
System.out.println(max);//55
```

**二、**

需求：生成10个1~100之间的随机数存入数组。

1）求出所有数据的和

2）求所有数据的平均数

3）统计有多少个数据比平均值小

代码示例：

```java
//分析：
//1.定义数组
int[] arr = new int[10];
//2.把随机数存入到数组当中
Random r = new Random();

for (int i = 0; i < arr.length; i++) {
    //每循环一次，就会生成一个新的随机数
    int number = r.nextInt(100) + 1;
    //把生成的随机数添加的数组当中
    //数组名[索引] = 数据;
    arr[i] = number;
}


// 1）求出所有数据的和
//定义求和变量
int sum = 0;
for (int i = 0; i < arr.length; i++) {
    //循环得到每一个元素
    //并把元素累加到sum当中
    sum = sum + arr[i];
}
System.out.println("数组中所有数据的和为：" + sum);


//2）求所有数据的平均数
int avg = sum / arr.length;
System.out.println("数组中平均数为：" + avg);



//3）统计有多少个数据比平均值小
int count = 0;
for (int i = 0; i < arr.length; i++) {
    if(arr[i] < avg){
        count++;
    }
}

//当循环结束之后，就表示我已经找到了所有的比平均数小的数据
System.out.println("在数组中，一共有" + count + "个数据，比平均数小");



//遍历数组，验证答案
for (int i = 0; i < arr.length; i++) {
    System.out.print(arr[i] + " ");
}
```

**三、**

需求：定义一个数组，存入1~5。要求打乱数组中所有数据的顺序。

代码示例：

```java
//1.定义数组存储1~5
int[] arr = {1, 2, 3, 4, 5};
//2.循环遍历数组，从0索引开始打乱数据的顺序
Random r = new Random();
for (int i = 0; i < arr.length; i++) {
    //生成一个随机索引
    int randomIndex = r.nextInt(arr.length);
    //拿着随机索引指向的元素 跟 i 指向的元素进行交换
    int temp = arr[i];
    arr[i] = arr[randomIndex];
    arr[randomIndex] = temp;
}
//当循环结束之后，那么数组中所有的数据已经打乱顺序了
for (int i = 0; i < arr.length; i++) {
    System.out.print(arr[i] + " ");
}
```  

##  方法

### 方法的概念

​	方法（method）是程序中最小的执行单元

* 注意：
  * 方法必须先创建才可以使用，该过程成为方法定义
  * 方法创建后并不是直接可以运行的，需要手动使用后，才执行，该过程成为方法调用

### 方法的定义和调用

**无参数方法定义和调用**

* 定义格式：

  ```java
  public static void 方法名 (   ) {
  	// 方法体;
  }
  ```



* 调用格式：

  ```java
  方法名();
  ```


* 注意：

  ​	方法必须先定义，后调用，否则程序将报错



###  带参数方法定义和调用

**带参数方法定义和调用**
* 定义格式：

  参数：由数据类型和变量名组成 -  数据类型 变量名

  参数范例：int a

  ```java
  public static void 方法名 (参数1) {
  	方法体;
  }
  
  public static void 方法名 (参数1, 参数2, 参数3...) {
  	方法体;
  }
  ```

* 范例：

  ```java
  public static void isEvenNumber(int number){
      ...
  }
  public static void getMax(int num1, int num2){
      ...
  }
  ```

  * 注意：

  		方法定义时，参数中的数据类型与变量名都不能缺少，缺少任意一个程序将报错
			
  		方法定义时，多个参数之间使用逗号( ，)分隔

* 调用格式：

  ```java
  方法名(参数)；
  
  方法名(参数1,参数2);
  ```

* 范例：

  ```java
  isEvenNumber(10);
  
  getMax(10,20);
  ```

  * 方法调用时，参数的数量与类型必须与方法定义中的设置相匹配，否则程序将报错 

**形参和实参**

1. 形参：方法定义中的参数

​          等同于变量定义格式，例如：int number

2. 实参：方法调用中的参数

​          等同于使用变量或常量，例如： 10  number  

### 带返回值方法的定义和调用

**带返回值方法定义和调用**

* 定义格式

  ```java
  public static 数据类型 方法名 ( 参数 ) { 
  	return 数据 ;
  }
  ```

* 范例

  ```java
  public static boolean isEvenNumber( int number ) {           
  	return true ;
  }
  public static int getMax( int a, int b ) {
  	return  100 ;
  }
  ```

  * 注意：
    * 方法定义时return后面的返回值与方法定义上的数据类型要匹配，否则程序将报错

* 调用格式

  ```java
  方法名 ( 参数 ) ;
  数据类型 变量名 = 方法名 ( 参数 ) ;
  ```

* 范例

  ```java
  isEvenNumber ( 5 ) ;
  boolean  flag =  isEvenNumber ( 5 ); 
  ```

  * 注意：
    * 方法的返回值通常会使用变量接收，否则该返回值将无意义



###  方法的注意事项

**方法的注意事项**

* 方法不能嵌套定义

  * 示例代码：

    ```java
    public class MethodDemo {
        public static void main(String[] args) {
    
        }
    
        public static void methodOne() {
    		public static void methodTwo() {
           		// 这里会引发编译错误!!!
        	}
        }
    }
    ```

* void表示无返回值，可以省略return，也可以单独的书写return，后面不加数据

  * 示例代码：

    ```java
    public class MethodDemo {
        public static void main(String[] args) {
    
        }
        public static void methodTwo() {
            //return 100; 编译错误，因为没有具体返回值类型
            return;	
            //System.out.println(100); return语句后面不能跟数据或代码
        }
    }
    ```  

### 方法重载

**方法重载**

* 方法重载概念

  方法重载指同一个类中定义的多个方法之间的关系，满足下列条件的多个方法相互构成重载

  * 多个方法在同一个类中
  * 多个方法具有相同的方法名
  * 多个方法的参数不相同，类型不同或者数量不同

* 注意：

  * 重载仅对应方法的定义，与方法的调用无关，调用方式参照标准格式
  * 重载仅针对同一个类中方法的名称与参数进行识别，与返回值无关，换句话说不能通过返回值来判定两个方法是否相互构成重载

* 正确范例：

  ```java
  public class MethodDemo {
  	public static void fn(int a) {
      	//方法体
      }
      public static int fn(double a) {
      	//方法体
      }
  }
  
  public class MethodDemo {
  	public static float fn(int a) {
      	//方法体
      }
      public static int fn(int a , int b) {
      	//方法体
      }
  }
  ```



**方法重载示例**

* 需求：使用方法重载的思想，设计比较两个整数是否相同的方法，兼容全整数类型（byte,short,int,long） 

* 思路：

  * ①定义比较两个数字的是否相同的方法compare()方法，参数选择两个int型参数
  * ②定义对应的重载方法，变更对应的参数类型，参数变更为两个long型参数
  * ③定义所有的重载方法，两个byte类型与两个short类型参数 
  * ④完成方法的调用，测试运行结果 

* 代码：

  ```java
  public class MethodTest {
      public static void main(String[] args) {
          //调用方法
          System.out.println(compare(10, 20));
          System.out.println(compare((byte) 10, (byte) 20));
          System.out.println(compare((short) 10, (short) 20));
          System.out.println(compare(10L, 20L));
      }
  
      //int
      public static boolean compare(int a, int b) {
          System.out.println("int");
          return a == b;
      }
  
      //byte
      public static boolean compare(byte a, byte b) {
          System.out.println("byte");
          return a == b;
      }
  
      //short
      public static boolean compare(short a, short b) {
          System.out.println("short");
          return a == b;
      }
  
      //long
      public static boolean compare(long a, long b) {
          System.out.println("long");
          return a == b;
      }
  
  }
  ```