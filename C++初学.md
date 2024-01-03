- 网课（黑马程序员）（共314节）：1，2，3，4，5，6，7，8，9，10，11，12，13，14，15，16，17，18，19，20，21，22，23，24，25，26，27，28，29，30，31，32，33，34，35，36，37，38，39，40，41，42，43，44，45，46，47，48，49，50，51，52，53，54，55，56，57，58，59，60，61，62，63，64，65，66，67，68，69，70，71，72，73，74，75，76，77，78，79，80，81，82，83，84，85，86，87，88，89，90，91，92，93，94，95，96，97，98，99，100，101，102，103，104，105，106，107，108，109，110，110，111，112，113，**114**，115，116，117，118，119，120，121，122，123，...，127，128，129，130，131，132，133，**134**，135，136，137，138，139，140，141，142，143，144，...，147，148，149，150，151，152，153，154，155，156，157，158，159，160，161，162，163，164，165，166，167，168，169，170，171，172，173，174，175
- 课程安排：
  - 第一阶段：C++基础入门，对C++有初步了解
    - 案例：通讯录管理系统
  - 第二阶段：C++核心编程，介绍C++面向对象编程，为大型项目做铺垫
    - 职工管理系统
  - 第三阶段：介绍C++泛型编程思想，以及STL的基本使用
    - 演讲比赛系统
  - 综合大案例：机房预约系统
- 注意事项：
  - 在typora中打开超链接的方式：Ctrl+鼠标左键点击


# 一.C++基础入门

## （一）.C++初识

### 1.第一个C++程序：

- 输出Hello World

- ```c++
  #include<iostream>
  using namespace std;
  
  int main()
  {
  	cout << "hello world" << endl;
      
  	system("pause");
  	return 0;
  }
  ```

### 2.注释`(comments)`

- 单行注释（通常放在一行代码上方，或一条语句末尾）

  - ```c++
    //单行注释
    ```

- 多行注释（通常放在一段代码上方）

  - ```c++
    /*
    多行注释
    */
    ```

### 3.变量`(variables)`

- 变量的作用：给一段指定的空间起名，方便操作这段内存
- 语法：`数据类型 变量名 = 初始值;`

### 4.常量`(constants)`

- 作用：用于记录程序中不可更改的数据

- C++定义常量的两种方法

  1. `#define 常量名 常量值`
     
  2. `const 数据类型 常量名 = 常量值`

### 5.关键字

- 再给变量或常量起名时，不得使用C++关键字

### 6.标识符`(identifier)`命名规则

- 标识符不能是关键字
- 标识符只能由字母、数字、下划线组成
- 第一个字符必须为字母或下划线，不能是数字
- 标识符区分大小写
- 建议：给变量起名时，最好能见名知意

## （二）.数据类型

### 1.整形

| 数据类型            | 占用空间                                               |
| ------------------- | ------------------------------------------------------ |
| short(短整型)       | 2字节                                                  |
| int(整形)           | 4字节                                                  |
| long(长整型)        | Windows系统为4字节,Linux(32位)为4字节、（64位）为8字节 |
| long long(长长整形) | 8字节                                                  |

### 2.sizeof关键字

- 作用：统计数据类型所占内存大小
- 语法：`sizeof(数据类型/变量)`

### 3.实型（浮点型）

- 作用：表示小数
- 浮点型变量分两种：
  1. 单精度浮点型float（通常在float类型后加一个f），占用4个字节空间，7位有效数字
     - 科学计数法：
       - `float f=3e2;//3*10^2`
       - `float f=3e-2;//3*0.1^2`
  2. 双精度浮点型double，占用8个字节，15~16位有效数字
- 默认情况下，输出一个小数，会显示出六位有效数字

### 4.字符型

- 作用：显示单个字符
- 语法：`char ch = 'a';`
- C和C++中字符型变量只占用一个字节
- 字符型变量并不是把字符本身放到内存中存储，而是把对应的ASCll编码放到存储单元中
- 常见错误：
  - `char ch = "b";//创建字符型变量时，要用单引号`
  - `char ch = 'abc';//创建字符型变量时，单引号内只能有一个字符`
- 查看字符型变量对应的ASCll编码
  - `cout << (int)ch << endl;`
  - a - 97
  - A - 65
- ASCll编码
  - 非打印字符：**0~31**分配给了控制字符，用于控制打印机等外围设备
  - 打印字符：**32~126**分配给了能在键盘上找到的字符，当查看或打印文档时会出现

### 5.转义字符

- 作用：用于表示一些不能显示出来的字符
- 常用：
  - \n：换行
  - \\\：输出一个反斜杠\
  - \t：水平制表符（跳到下一个tab位置）

### 6.字符串型

- 作用：表示一串字符

- 两种风格：
  1. C语言风格字符串：`char 变量名[] = "字符串值"`
  2. C++风格字符串：`string 变量名 = "字符串值"`
     - 需要包含头文件`#include<string>`
  

#### （1）字符串比较

- 如果要比较的对象是两个string，则利用函数 `compare()`

  - 两个字符串相等时返回0
  - 两个字符串不相等时：
    - 若s1长度长，则返回1
    - 若s1长度短，则返回-1

- 也可以直接使用`==`号进行比较

- 示例：

  - ```c++
    #include<iostream>
    #include<string>
    using namespace std;
    
    int main()
    {
    	string s1 = "abc";
    	string s2 = "abc";
    	string s3 = "ab";
    	string s4 = "abcd";
    	cout << s1.compare(s2) << endl;	//两个字符串相等时返回0
    	cout << s1.compare(s3) << endl;	//两个字符串不相等时,若s1长度长，则返回1
    	cout << s1.compare(s4) << endl;	//两个字符串不相等时,若s1长度短，则返回-1
    	cout << (s1 == s2) << endl;	//也可以用等于号直接比较，相等时返回1
    	cout << (s1 == s3) << endl;	//不相等时返回0
    
    	system("pause");
    	return 0;
    }
    ```

### 7.布尔类型bool

- 作用：代表真或假的值
- bool类型只有两个值：
  - true---真（1）
  - false---假（0）
- bool类型只占1个字节大小
- 创建bool数据类型
  - `bool flag = true`
- 布尔类型，非0都是真

### 8.数据的输入输出

- 作用：用于从键盘获取数据

- 关键字：`cin`

- 语法：`cin >> 变量`

- 不同数据类型的输入

  1. 整形

     - ```c++
       int a = 0;
       cout << "请给整型变量a赋值" << endl;
       cin >> a;
       cout << "整型变量a = " << a << endl;
       ```

  2. 浮点型

     - ```c++
       float f = 3.14f;
       cout << "请给浮点型变量f赋值" << endl;
       cin >> f;
       cout << "浮点型变量f = " << f << endl;
       ```

  3. 字符型

     - ```c++
       char ch = 'a';
       cout << "请给字符型变量ch赋值" << endl;
       cin >> ch;
       cout << "字符型变量ch = " << ch << endl;
       ```

  4. 字符串型

     - ```c++
       string str = "abc";
       cout << "请给字符串型str赋值" << endl;
       cin >> str;
       cout << "字符串型str = " << str << endl;
       ```

  5. 布尔数据类型

     - ```c++
       bool flag = false;
       cout << "请给布尔类型flag赋值" << endl;
       cin >> flag;
       cout << "布尔类型flag = " << flag << endl;
       ```

## （三）.运算符`(operators)`

### 1.算术运算符

- +
- -
- *
- /
  - 除数不能为0
  - 两个整数相除仍然是整数
- %
  - 除数不能为0，0也不能取模
  - 两个小数不能作取模运算
  - 只有整型变量可以作取模运算
- ++a
- a++
- --a
- a--

### 2.赋值运算符

- +=
- -=
- *=
- /=
- %=

### 3.比较运算符

- ==

- !=

- <

- `>`

- <=

- `>=`

### 4.逻辑运算符

- !		非
- &&    与
- ||       或

## （四）.程序流程结构

### 1.顺序结构

#### （1）if语句

- 作用：执行满足条件的语句

- if语句的三种格式：

  - 单行格式

    - ```c++
      if(条件)
      {
          条件满足的语句
      }
      ```

  - 多行格式

    - ```c++
      if(条件)
      {
          条件满足的语句
      }
      else
      {
          条件不满足的语句
      }
      ```

  - 多条件

    - ```c++
      if(条件1)
      {
          条件1满足后执行的语句
      }
      else if(条件2)
      {
          条件2满足后执行的语句
      }
      ...
      else
      {
          条件都不满足执行的语句
      }
      ```

- 嵌套if语句

#### （2）三目运算符

- 作用：通过三目运算符实现简单判断

- 语法：`表达式1 ？ 表达式2 ：表达式3`

- 解释：

  - 如果表达式1为真，执行表达式2，返回表达式2的结果
  - 如果表达式1为假，执行表达式3，返回表达式3的结果

- 在C++中三目运算符返回的是变量，可以继续赋值

  - ```c++
    int a = 10;
    int b = 20;
    int c = 0;
    (a < b ? a : b) = 100;
    cout << "a = " << a << endl;
    cout << "b = " << b << endl;
    ```

#### （3）switch语句

- 作用：执行多条件分支语句

- 语法：

  - ```c++
    switch(表达式)
    {
        case 结果1:
            执行语句;break;
        case 结果2:
            执行语句;break;
        ...
        default: 
            执行语句;break;
    }
    ```

- switch语句优缺点：

  - 缺点：判断是只能是整型或字符型，不可以是一个区间；
  - 优点：结构清晰，执行效率高

- 注意：case中如果没有break，程序会一直向下执行

### 2.循环结构

#### （1）while循环语句

- 语法：

  - ```c++
    while(循环条件)
    {
        循环语句
    }
    ```

- 注意：必须提供跳出循环的出口

- while循环练习案例：猜数字

  - 文件：[02.循环练习案例：猜数字.cpp](https://github.com/zzx051900/C-/blob/a6acf6b607c39e605b74af9503e11088bb27613e/C%2B%2B%E7%A8%8B%E5%BA%8F%E7%BB%83%E4%B9%A0%E4%BB%A3%E7%A0%81/2.%E5%BE%AA%E7%8E%AF%E7%BB%93%E6%9E%84%E6%A1%88%E4%BE%8B-%E7%8C%9C%E6%95%B0%E5%AD%97.cpp)
  
  - 代码：
  
    - ```c++
      #include<iostream>
      #include<ctime>//time系统时间的头文件
      using namespace std;
      
      int main()
      {
      	//添加随机数种子，利用当前系统时间生成随机数，防止每次随机数都一样
      	srand((unsigned int)time(NULL));
      
      	//系统生成随机数(伪随机数）
      	int num = rand() % 100 + 1;	//rand()%100，生成0~99的随机数
      	//cout << num << endl;
      
      	int val = 0;
      
      	while (1)
      	{
      		//玩家进行猜测
      		cin >> val;
      
      		//判断玩家猜测
      		if (val > num)
      		{
      			cout << "猜测过大" << endl;
      		}
      		else if (val < num)
      		{
      			cout << "猜测过小" << endl;
      		}
      		else
      		{
      			cout << "恭喜您猜对了" << endl;
      			break;
      		}
      	}
      
      	system("pause");
      	return 0;
      }
      ```

#### （2）do...while循环语句

- 语法：

  - ```c++
    do
    {
        循环语句
    }while(循环条件);
    ```

- 注意：与while的区别在于do...while会先执行一次循环语句，再判断条件

- 文件：[3.循环结构案例-水仙花数.cpp](https://github.com/zzx051900/C-/blob/a6acf6b607c39e605b74af9503e11088bb27613e/C%2B%2B%E7%A8%8B%E5%BA%8F%E7%BB%83%E4%B9%A0%E4%BB%A3%E7%A0%81/3.%E5%BE%AA%E7%8E%AF%E7%BB%93%E6%9E%84%E6%A1%88%E4%BE%8B-%E6%B0%B4%E4%BB%99%E8%8A%B1%E6%95%B0.cpp)

- 代码：

  - ```c++
    /*
    案例描述：水仙花数是指一个3位数，它的每个位上的数字的3次幂之和等于它本身
    例如：1^3+5^3+3^3=153
    使用do...while语句，求出所有3位数中的水仙花数
    */
    #include<iostream>
    
    using namespace std;
    
    int main()
    {
    	int m = 100;//3位数，从100开始
    
    	int a = 0;//获取百位数字
    	int b = 0;//获取十位数字
    	int c = 0;//获取个位数字
    
    	do
    	{
    		a = m / 100;
    		b = m / 10 % 10;
    		c = m % 10;
    		if (a*a*a + b*b*b + c*c*c == m)
    		{
    			cout << m << endl;
    		}
    		m++;
    	} while (m < 1000);
    
    	system("pause");
    	return 0;
    }
    ```


#### （3）for循环

- 语法：

  - ```c++
    for(起始表达式;条件表达式;末尾循环体)
    {
        循环语句
    }
    ```
  
- 文件：[4.循环结构案例-敲桌子.cpp](https://github.com/zzx051900/C-/blob/a6acf6b607c39e605b74af9503e11088bb27613e/C%2B%2B%E7%A8%8B%E5%BA%8F%E7%BB%83%E4%B9%A0%E4%BB%A3%E7%A0%81/4.%E5%BE%AA%E7%8E%AF%E6%A1%88%E4%BE%8B-%E6%95%B2%E6%A1%8C%E5%AD%90.cpp)

  - ```c++
    /*
    案例描述：
    从1开始数到数字100，如果数字中含有7，或该数字是7的倍数，
    我们打印敲桌子，其余数字直接打印输出
    */
    #include<iostream>
    
    using namespace std;
    
    int main()
    {
    
    	for (int i = 1; i <= 100; i++)
    	{
    		//个位是7（i % 10 == 7）    
    		//十位是7（i / 10 == 7）
    		//7的倍数（i % 7 == 0）
    		if (i % 10 == 7 || i / 10 == 7 || i % 7 == 0)
    		{
    			cout << i << " 敲桌子" << endl;
    		}
    		else
    		{
    			cout << i << endl;
    		}
    	}
    	system("pause");
    	return 0;
    }
    ```


#### （4）嵌套循环

- 在循环里再嵌套一层循环

### 3.跳转语句

#### （1）break语句

- 作用：用于跳出选择循环或循环结构
- break使用的时机；
  - 出现在switch条件语句，终止case并跳出switch
  - 出现在循环语句，跳出当前循环
  - 出现在嵌套循环，跳出最内层的循环

#### （2）continue语句

- 在循环语句中，跳过本次循环中余下尚未执行的语句，继续执行下一次循环

#### （3）goto语句

- 作用：无条件跳转语句
- 语法：
  - `goto 标记;`    
  - `标记：`

## （五）.数组`(arrays)`

### 1.一维数组

#### （1）一维数组的定义方式

- 三种方式：

  1. `数据类型 数组名[数组长度];`
   - 全局数组，未初始化时，默认值都是 0
     
   - 局部数组，未初始化时，默认值为随机的不确定的值（-858993460）
     
2. `数据类型 数组名[数组长度] = {值1,值2,...};`
     - 如果在数组初始化数据时，没有全部填写完，会用0来填补数据
   
  3. `数据类型 数组名[] = {值1,值2,...};`
- 这种定义方式必须有初始长度

#### （2）一维数组的数组名

- 用途：
  1. 统计整个数组在内存中的长度
     - `sizeof(arr);//整个数组占用空间`
     - `sizeof(arr[0]);//每个元素所占内存空间`
     - `sizeof(arr)/sizeof(arr[0]);//数组中元素个数`
  2. 获取数组在内存中的首地址
     - `cout << arr <<endl;`
- 注意：数组名是常量，不可以赋值

#### （3）一维数组案例

1. 文件：[5.一维数组案例-寻找最大值.cpp](https://github.com/zzx051900/C-/blob/a39f5c2707dd177f4d6719720c9eadf0d43ca457/C%2B%2B%E7%A8%8B%E5%BA%8F%E7%BB%83%E4%B9%A0%E4%BB%A3%E7%A0%81/5.%E4%B8%80%E7%BB%B4%E6%95%B0%E7%BB%84%E6%A1%88%E4%BE%8B-%E5%AF%BB%E6%89%BE%E6%9C%80%E5%A4%A7%E5%80%BC.cpp)

   - 代码：

     - ```c++
       //一维数组案例：寻找最大值
       #include<iostream>
       using namespace std;
       
       int main()
       {
       	//1.创建数组
       	int arr[5] = { 50, 40, 60, 70, 90 };
       	//2.寻找最大值
       	int max = 0;//存放最大值
       	for (int i = 0; i < 5; i++)
       	{
       		if (arr[i]>max)
       			max = arr[i];//如果访问的元素比我认定的元素大，则更新最大值
       	}
       	//3.输出最大值
       	cout << "最大值为：" << max << endl;
       	system("pause");
       	return 0;
       }
       ```

2. 文件：[6.一维数组案例-数组元素逆置.cpp](https://github.com/zzx051900/C-/blob/a39f5c2707dd177f4d6719720c9eadf0d43ca457/C%2B%2B%E7%A8%8B%E5%BA%8F%E7%BB%83%E4%B9%A0%E4%BB%A3%E7%A0%81/6.%E4%B8%80%E7%BB%B4%E6%95%B0%E7%BB%84%E6%A1%88%E4%BE%8B-%E6%95%B0%E7%BB%84%E5%85%83%E7%B4%A0%E9%80%86%E7%BD%AE.cpp)

   - 代码：

     - ```c++
       //一维数组案例：数组元素逆置
       //案例描述：请声明一个5个元素的数组，并且将元素逆置
       #include<iostream>
       
       using namespace std;
       
       int main()
       {
       	int arr[5] = { 9, 3, 7, 2, 8 };
       	int temp = 0;//用于交换时暂时存放元素
       
       	for (int i = 0; i < 5; i++)
       	{
       		cout << arr[i] << " ";
       	}
       	cout << endl;
       
       	for (int i = 0; i < 5 / 2; i++)//i小于数组元素个数的一半
       	{
       		temp = arr[i];
       		arr[i] = arr[4 - i];
       		arr[4 - i] = temp;
       	}
       
       	for (int i = 0; i < 5; i++)
       	{
       		cout << arr[i] << " ";
       	}
       	system("pause");
       	return 0;
       }
       ```

#### （4）冒泡排序（升序）

- 算法思想：
  1. 比较相邻的元素，如果第一个比第二个大，就交换它们两个
  2. 对每一对相邻元素做相同工作，执行完毕后，找到第一个最大值
  3. 重复以上步骤，由于每次执行一轮会将目前最大值放在最后，所以每次执行次数减一，直到不需要比较
  
- 文件：[7.冒泡排序.cpp](https://github.com/zzx051900/C-/blob/a39f5c2707dd177f4d6719720c9eadf0d43ca457/C%2B%2B%E7%A8%8B%E5%BA%8F%E7%BB%83%E4%B9%A0%E4%BB%A3%E7%A0%81/7.%E5%86%92%E6%B3%A1%E6%8E%92%E5%BA%8F.cpp)

- 代码：

  - ```c++
    //冒泡排序（升序）
    #include<iostream>
    using namespace std;
    
    int main()
    {
    	int arr[] = { 2, 4, 3, 5, 6, 8, 9, 7, 1, 10 };
    	int sz = sizeof(arr) / sizeof(arr[0]);
    	//排序前输出
    	for (int i = 0; i<sz; i++)
    	{
    		cout << arr[i] << " ";
    	}
    	cout << endl;
    	int i = 0;//用于外层循环，表示趟数
    	int j = 0;//用于内层循环，表示第几个数
    	int tmp = 0;//用于交换元素
    	for (i = 0; i<sz - 1; i++)//n个元素需要n—1次循环，，每一趟将一个元素交换到它应该在的最终位置
    	{
    		for (j = 0; j<sz - 1 - i; j++)//每趟循环都要从头开始，都要将j置0
    		{
    			if (arr[j]>arr[j + 1])
    			{
    				tmp = arr[j];
    				arr[j] = arr[j + 1];
    				arr[j + 1] = tmp;
    			}
    		}
    	}
    	//排序后输出.
    
    	for (int i = 0; i<sz; i++)
    	{
    		cout << arr[i] << " ";
    	}
    	system("pause");
    	return 0;
    }
    ```


### 2.二维数组

#### （1）二维数组定义方式

- 四种方式：
  1. `数据类型 数组名[行数][列数];`
  2. `数据类型 数组名[行数][列数] = {{数据1,数据2},{数据3,数据4}};`
  3. `数据类型 数组名[行数][列数] = {数据1,数据2,数据3,数据4};`
  4. `数据类型 数组名[][列数] = {数据1,数据2,数据3,数据4};`

#### （2）二维数组的数组名

- 作用：
  - 查看二维数组所占内存空间
    - `sizeof(arr);//二维数组占用空间`
    - `sizeof(arr[0]);//第一行所占内存空间`
    - `sizeof(arr)/sizeof(arr[0]);//二维数组行数`
    - `sizeof(arr[0])/sizeof(arr[0][0]);//二维数组列数`
    - `sizeof(arr)/sizeof(arr[0][0]);//数组中元素个数`
  - 查看二维数组首地址

## （六）.函数`(functions)`

### 1.函数的作用

- 将一段经常使用的代码封装起来，减少重复代码；一个较大的程序，一般分为若干个程序块，每个模块实现特定的功能

### 2.函数的定义

- 五个步骤：

  1. 返回值类型
  2. 函数名
  3. 参数列表
  4. 函数体语句
  5. return表达式

- 语法：

  - ```c++
    返回时类型 函数名(参数列表)
    {
        函数体语句;
        return表达式
    }
    ```

### 3.函数的调用

- 功能：使用定义好的函数
- 语法：`函数名(参数)`

### 4.值传递

- 值传递，就是函数调用时，将实参传递给形参
- 值传递时，如果形参发生改变，并不会影响实参

### 5.函数的常见样式

- 四种：
  - 无参无返
  - 有参无返
  - 无参有返
  - 有参有返

### 6.函数声明

- 作用：告诉编译器函数名称及如何调用函数，函数的实际主体可以单独定义
- 函数的声明可以多次，但是函数的定义只有一次

### 7.函数的分文件编写

- 作用：让代码结构更加清晰
- 四个步骤：
  1. 创建后缀名为.h的头文件
  2. 创建后缀名为.cpp的源文件
  3. 在头文件中写函数的声明
  4. 在源文件中写函数的定义

## （七）.指针`(pointers)`

### 1.指针的作用

- 作用：通过指针间接访问内存
- 内存编号从0开始记录，一般用十六进制表示
- 可以用指针变量保存地址

### 2.指针变量的定义和使用

- `指针定义的语法：数据类型 *指针变量名`

- ```c++
  int a = 10;
  int *p = &a;//指针p记录变量a的地址
  ```

- 使用指针：通过解引用的方式找到指针指向的内存；指针前加 * 表示解引用，找到指针指向的内存中的数据

- `*p = 100;`

### 3.指针所占内存空间

- 在32位操作系统下，占用4个字节
- 在64位操作系统下，占用8个字节

### 4.空指针和野指针

- 空指针：指针变量指向内存中编号为0的空间
  - 用途：初始化指针变量
  - 注意空指针指向的内存不可以访问（内存编号0~255为系统占用内存，不允许用户访问）
- 野指针：指针变量指向非法的内存空间
- 总结：空指针和野指针都不是我们要访问的空间，因此不要访问

### 5.const修饰指针

- 三种情况：

  1. const修饰指针 （常量指针）

     - ```c++
       const放在指针变量的*的左边时，修饰的是*p,也就是说，不能通过p改变*p的值    
           eg：const int *p=&num;        
       		*p=20;//不可以        
       		p=&n;//可以
       ```

     - 特点：指针的指向可以修改，但是指针指向的值不可以修改

  2. const修饰常量 （指针常量）

     - ```c++
       const放在指针变量*的右边时，修饰的是p本身，即p的地址无法改变    
           eg：int * const p=&num;       
       		*p=20;//可以       
       		p=&20;//不可以
       ```

     - 特点：指针的指向不可以修改，但是指针指向的值可以修改

  3. const既修饰指针，又修饰常量

     - ```c++
       const int * const p=&num;//此时内容和地址都不能更改
       ```

### 6.指针和数组

- 利用指针访问数组元素

  - ```c++
    int arr[] = {1,2,3,4,5,6,7,8,9,10};
    int *p = arr;
    cout << *p << endl;//输出数组第一个元素1
    p++;//指针向后偏移4个字节
    cout << *p << endl;//输出数组第二个元素2
    //遍历输出
    p = arr;
    int sz = sizeof(arr)/sizeof(arr[0]);
    while(sz)
    {
        cout << *p <<endl;
        p++;
        sz--;
    }
    ```

- 字符数组字符串的字面值可以赋值给`char*`指针，但不可以修改其中的任何元素，因为该指针指向的是一个`const`字符数组

  - ```c++
    char arr[] = "hello world";
    cout << arr << endl;
    arr[0] = 'a';
    cout << arr << endl;
    
    char* p = "hello world";
    cout << *p << endl;	//输出数组第一个元素
    p[0] = 'h';	//非法操作
    //cout << *p << endl;	//无法正常输出
    ```


### 7.指针和函数

- 作用：利用指针作函数参数，可以修改实参的值

  - ```c++
    void swap(int* p1, int* p2)
        //这里的int* p1是表明p1是一个指针，也可写成int *p1，但这里的*p1不是解引用的意思，仅仅还是表明p1是一个指针
    {
    	int temp = 0;
    	temp = *p1;
    	*p1 = *p2;
    	*p2 = temp;
    }
    int main()
    {
    	int a = 10, b = 20;
    	cout << "a=" << a << endl;
    	cout << "b=" << b << endl;
    	swap(&a, &b);
    	cout << "a=" << a << endl;
    	cout << "b=" << b << endl;
    	system("pause");
    	return 0;
    }
    ```


### 8.指针、数组、函数

- 案例描述：封装一个函数，利用冒泡排序，实现对整型数组的排序

- 文件：[8.指针配合数组和函数案例-冒泡排序.cpp](https://github.com/zzx051900/C-/blob/a39f5c2707dd177f4d6719720c9eadf0d43ca457/C%2B%2B%E7%A8%8B%E5%BA%8F%E7%BB%83%E4%B9%A0%E4%BB%A3%E7%A0%81/8.%E6%8C%87%E9%92%88%E9%85%8D%E5%90%88%E6%95%B0%E7%BB%84%E5%92%8C%E5%87%BD%E6%95%B0%E6%A1%88%E4%BE%8B-%E5%86%92%E6%B3%A1%E6%8E%92%E5%BA%8F.cpp)

- 代码：

  - ```c++
    #include<iostream>
    
    using namespace std;
    
    void bubbleSort(int* arr, int sz)//冒泡排序，未优化，原始版本
    {
    	for (int i = 0; i < sz - 1; i++)//sz个元素，需要循环sz-1趟
    	{
    		for (int j = 0; j < sz - 1 - i; j++)//需要比较的数每次减少一个
    		{
    			if (arr[j]>arr[j + 1])
    			{
    				int temp = arr[j];
    				arr[j] = arr[j + 1];
    				arr[j + 1] = temp;
    			}
    		}
    	}
    }
    
    void printArray(int* arr, int sz)//遍历输出数组元素
    {
    	for (int i = 0; i < sz; i++)
    		cout << arr[i] << " ";
    	cout << endl;
    }
    
    int main()
    {
    	int arr[] = { 5, 6, 9, 4, 3, 2, 8, 7, 1, 10 };
    	int sz = sizeof(arr) / sizeof(arr[0]);//数组元素个数
    	printArray(arr, sz);//输出排序前数组元素
    	bubbleSort(arr, sz);
    	printArray(arr, sz);//输出排序后数组元素
    	system("pause");
    	return 0;
    }
    ```


## （八）.结构体

### 1.结构体基本概念

- 结构体属于用户自定义数据类型，允许用户储存不同的数据类型

### 2.结构体定义和使用

- 语法：

  - ```c++
    struct 结构体名
    {
        结构体成员列表
    };
    ```

- 通过结构体创建变量的三种方式：

  1. `struct 结构体名 变量名;`（常用）
  2. `struct 结构体名 变量名 = {成员1值,成员2值,...};`（常用）
  3. `定义结构体时顺便创造变量`（少用）

- ```c++
  #include<iostream>
  #include<string>
  using namespace std;
  struct Student
  {
  	string name;
  	int age;
  	int score;
  }s3;
  int main()
  {
  	//第一种创建变量方式
  	struct Student s1;
  	s1.name = "aaa";
  	s1.age = 18;
  	s1.score = 100;
  	cout << "姓名：" << s1.name << " 年龄：" << s1.age << " 分数：" << s1.score << endl;
  	//第二种创建变量方式
  	struct Student s2 = { "bbb", 19, 90 };
  	cout << "姓名：" << s2.name << " 年龄：" << s2.age << " 分数：" << s2.score << endl;
  	//第三种方式，定义结构体时顺便创造变量
  	s3.name = "ccc";
  	s3.age = 20;
  	s3.score = 95;
  	cout << "姓名：" << s3.name << " 年龄：" << s3.age << " 分数：" << s3.score << endl;
  	system("pause");
  	return 0;
  }
  ```
  
- 注意：

  - 创建结构体变量的时候，关键字struct可以省略
  - 结构体变量用操作符"."访问成员

### 3.结构体数组

- 将自定义的结构体放入数组中方便维护

- 语法：

  - ```c++
    struct 结构体名 数组名[元素个数] = {{},{},...,{}};
    ```

- ```c++
  //1.定义结构体
  struct Student
  {
  	string name;
  	int age;
  	int score;
  };
  //2.创建结构体数组,并顺便给结构体数组中的元素赋值
  struct Student stuArr[] =
  {
      {"aaa",18,90},
      {"bbb",19,95},
      {"ccc",20,100}
  }
  //3.也可后续再给元素赋值
  stuArr[2].name = "ddd";
  stuArr[2].age = 21;
  stuArr[2].score = 85;
  //4.遍历结构体数组
  for(int i = 0;i < 3;i++)
  {
      cout << "姓名:" << stuArr[i].name
           << " 年龄:" << stuArr[i].age
           << " 分数:" << stuArr[i].score <<endl;
  }
  ```

### 4.结构体指针

- 作用：通过指针访问结构体中的成员

- 使用操作符`->`可以通过结构体指针访问结构体属性

- ```c++
  //1.定义结构体
  struct Student
  {
  	string name;
  	int age;
  	int score;
  };
  //2.创建结构体变量
  struct Student s = {"aaa",18,90};
  //3.通过指针指向结构体变量
  struct Student *p = &s;
  //4.通过指针访问结构体变量中的数据
  cout << "姓名:" << p->name
  	<< " 年龄:" << p->age
  	<< " 分数:" << p->score << endl;
  ```

### 5.结构体嵌套结构体

- 作用：结构体中的成员可以是另一个结构体

- ```c++
  struct Student
  {
  	string name;
  	int age;
  	int score;
  };
  struct Teacher
  {
      int id;
      string name;
      int age;
      struct Student stu;
  }
  //创建老师
  struct Teacher t;
  t.stu.name = "aaa";
  ```

### 6.结构体作函数参数

- 作用：将结构体作为参数向函数中传递

- 两种传递方式：

  - 值传递
  - 地址传递

- ```c++
  #include<iostream>
  #include<string>
  using namespace std;
  
  struct Student
  {
  	string name;
  	int age;
  	int score;
  };
  
  //输出结构体数组元素
  //值传递
  void printStu1(struct Student s)
  {
  	cout << "姓名:" << s.name
  		<< " 年龄:" << s.age
  		<< " 分数:" << s.score << endl;
  }
  
  //地址传递
  void printStu2(struct Student* p)
  {
  	cout << "姓名:" << p->name
  		<< " 年龄:" << p->age
  		<< " 分数:" << p->score << endl;
  }
  
  int main()
  {
  	struct Student s1;
  	s1.name = "aaa";
  	s1.age = 18;
  	s1.score = 100;
  
  	//值传递
  	printStu1(s1);
  
  	//地址传递
  	printStu2(&s1);
  	struct Student *p = &s1;
  	printStu2(p);
  	
  	system("pause");
  	return 0;
  }
  
  ```

- 总结：如果不想修改主函数中的数据，用值传递；反之用地址传递

### 7.结构体中const使用场景

- 作用：用const来防止误操作

- 将函数中的形参改为指针，可以减少内存空间，不会复制新的副本

  - 如果函数不需要修改结构体元素的值，在形参指针前加入const之后，一旦有修改的操作，就会报错，可以防止误操作

- ```c++
  //地址传递
  void printStu2(const struct Student* p)
  {
  	stu->age = 50;//会报错，操作失败
      cout << "姓名:" << p->name
  		<< " 年龄:" << p->age
  		<< " 分数:" << p->score << endl;
  }
  ```

### 8.结构体案例

- 案例1：
  - 案例描述：学校正在做毕设项目，每名老师带领5个学生，总共有3名老师，需求如下：
    - 设计学生和老师的结构体，其中在老师的结构体中有老师的姓名和一个存放5名学生的数组作为成员
    - 学生的成员有姓名、考试分数
    - 创建数组存放3名老师，通过函数给每个老师及所带学生赋值
    - 最终打印出老师数据以及老师所带学生的数据
    
  - 文件：
    - [9.1结构体案例1（视频讲解版）.cpp](https://github.com/zzx051900/C-/blob/a39f5c2707dd177f4d6719720c9eadf0d43ca457/C%2B%2B%E7%A8%8B%E5%BA%8F%E7%BB%83%E4%B9%A0%E4%BB%A3%E7%A0%81/9.1%E7%BB%93%E6%9E%84%E4%BD%93%E6%A1%88%E4%BE%8B1%EF%BC%88%E8%A7%86%E9%A2%91%E8%AE%B2%E8%A7%A3%E7%89%88%EF%BC%89.cpp)
    
      - 代码：
    
        - ```c++
          /*
          案例描述：学校正在做毕设项目，每名老师带领5个学生，总共有3名老师，需求如下：
          - 设计学生和老师的结构体，其中在老师的结构体中有老师的姓名和一个存放5名学生的数组作为成员
          - 学生的成员有姓名、考试分数
          - 创建数组存放3名老师，通过函数给每个老师及所带学生赋值
          - 最终打印出老师数据以及老师所带学生的数据
          */
          //注意：没有实现具体输入
          #include<iostream>
          #include<string>
          using namespace std;
          
          //学生的结构体
          struct Student
          {
          	string sName;
          	int score;
          };
          
          
          // 老师的结构体
          struct Teacher
          {
          	string tName;
          	struct Student sArray[5];
          };
          
          //赋值函数,开辟空间并赋值
          void allocateSpace(struct Teacher tArray[], int sz)
          {
          	string nameSeed = "ABCDE";
          	for (int i = 0; i < sz; i++)
          	{
          		tArray[i].tName = "Teacher_";
          		tArray[i].tName += nameSeed[i];//只能叫做给老师做了编号，并不能叫做输入老师姓名
          		for (int j = 0; j < 5; j++)
          		{
          			tArray[i].sArray[j].sName = "Student_";
          			tArray[i].sArray[j].sName += nameSeed[j];
          			tArray[i].sArray[j].score = 60;
          		}
          	}
          }
          
          //打印所有老师及所带学生的信息
          void printInfo(struct Teacher tArray[], int sz)
          {
          	for (int i = 0; i < sz; i++)
          	{
          		cout << "老师姓名：" << tArray[i].tName << endl;
          		for (int j = 0; j < 5; j++)
          		{
          			cout << "\t学生姓名:" << tArray[i].sArray[j].sName << " 分数：" << tArray[i].sArray[j].score << endl;
          		}
          	}
          	cout << endl;
          }
          
          int main()
          {
          	//创建3名老师的数组
          	struct Teacher tArray[3];
          
          	//通过函数给3名老师的信息赋值，并给老师所带的学生信息赋值
          	int sz = sizeof(tArray) / sizeof(tArray[0]);
          	allocateSpace(tArray, sz);
          
          	//打印所有老师及所带学生的信息
          	printInfo(tArray, sz);
          
          	system("pause");
          	return 0;
          }
          ```
    
    - [9.2结构体案例1（改进版）.cpp](https://github.com/zzx051900/C-/blob/a39f5c2707dd177f4d6719720c9eadf0d43ca457/C%2B%2B%E7%A8%8B%E5%BA%8F%E7%BB%83%E4%B9%A0%E4%BB%A3%E7%A0%81/9.2%E7%BB%93%E6%9E%84%E4%BD%93%E6%A1%88%E4%BE%8B1%EF%BC%88%E6%94%B9%E8%BF%9B%E7%89%88%EF%BC%89.cpp)
    
      - 代码：
    
        - ```c++
          /*
          案例描述：学校正在做毕设项目，每名老师带领5个学生，总共有3名老师，需求如下：
          - 设计学生和老师的结构体，其中在老师的结构体中有老师的姓名和一个存放5名学生的数组作为成员
          - 学生的成员有姓名、考试分数
          - 创建数组存放3名老师，通过函数给每个老师及所带学生赋值
          - 最终打印出老师数据以及老师所带学生的数据
          */
          //实现了具体输入
          #include<iostream>
          #include<string>
          using namespace std;
          
          //学生的结构体
          struct Student
          {
          	string sName;
          	int score;
          };
          
          // 老师的结构体
          struct Teacher
          {
          	string tName;
          	struct Student sArray[5];
          };
          
          //赋值函数,开辟空间并赋值
          void allocateSpace(struct Teacher tArray[], int sz)
          {
          	for (int i = 0; i < sz; i++)
          	{
          
          		cin >> tArray[i].tName;
          		for (int j = 0; j < 5; j++)
          		{
          			cin >> tArray[i].sArray[j].sName;
          			cin >> tArray[i].sArray[j].score;
          		}
          	}
          }
          
          //打印所有老师及所带学生的信息
          void printInfo(struct Teacher tArray[], int sz)
          {
          	for (int i = 0; i < sz; i++)
          	{
          		cout << "老师姓名：" << tArray[i].tName << endl;
          		for (int j = 0; j < 5; j++)
          		{
          			cout << "\t学生姓名:" << tArray[i].sArray[j].sName << " 分数：" << tArray[i].sArray[j].score << endl;
          		}
          	}
          	cout << endl;
          }
          
          int main()
          {
          	//创建3名老师的数组
          	struct Teacher tArray[3];
          
          	//通过函数给3名老师的信息赋值，并给老师所带的学生信息赋值
          	int sz = sizeof(tArray) / sizeof(tArray[0]);
          	allocateSpace(tArray, sz);
          
          	//打印所有老师及所带学生的信息
          	printInfo(tArray, sz);
          
          	system("pause");
          	return 0;
          }
          ```
  
- 案例2：
  - 案例描述：
    - 设计一个英雄的结构体，包括成员姓名，年龄，性别
    - 创建结构体数组，存放5名英雄
    - 通过冒泡排序，将数组中的英雄按照年龄进行升序排序，最终打印排序后的结果
    
  - 文件：[10.结构体案例2.cpp](https://github.com/zzx051900/C-/blob/a39f5c2707dd177f4d6719720c9eadf0d43ca457/C%2B%2B%E7%A8%8B%E5%BA%8F%E7%BB%83%E4%B9%A0%E4%BB%A3%E7%A0%81/10.%E7%BB%93%E6%9E%84%E4%BD%93%E6%A1%88%E4%BE%8B2.cpp)
  
  - 代码：
  
    - ```c++
      /*
      案例描述：
      - 设计一个英雄的结构体，包括成员姓名，年龄，性别
      - 创建结构体数组，存放5名英雄
      - 通过冒泡排序，将数组中的英雄按照年龄进行升序排序，最终打印排序后的结果
      */
      #include<iostream>
      #include<string>
      using namespace std;
      
      
      // 英雄的结构体
      struct Hero
      {
      	string name;
      	int age;
      	string sex;
      };
      
      //打印所有英雄的信息
      void printInfo(struct Hero heroArray[], int sz)
      {
      	for (int i = 0; i < 5; i++)
      	{
      		cout << "英雄姓名:" << heroArray[i].name << " 年龄：" << heroArray[i].age << " 性别：" << heroArray[i].sex << endl;
      	}
      	cout << endl;
      }
      
      //冒泡排序
      void bubblesort(struct Hero heroArray[], int sz)
      {
      	struct Hero temp;
      	for (int i = 0; i < sz - 1; i++)
      	{
      		for (int j = 0; j < sz - 1 - i; j++)
      		{
      			if (heroArray[j].age > heroArray[j + 1].age)//交换的是整个结构体变量，不只是交换年龄
      			{
      				temp = heroArray[j];
      				heroArray[j] = heroArray[j + 1];
      				heroArray[j + 1] = temp;
      			}
      		}
      	}
      }
      
      int main()
      {
      	//创建5名英雄的数组
      	struct Hero heroArray[5] =
      	{
      		{ "aaa", 20, "男" },
      		{ "bbb", 18, "女" },
      		{ "ccc", 26, "男" },
      		{ "ddd", 24, "男" },
      		{ "eee", 19, "女" },
      	};
      
      	int sz = sizeof(heroArray) / sizeof(heroArray[0]);
      	//打印排序前所有英雄的信息
      	printInfo(heroArray, sz);
      
      	//冒泡排序
      	bubblesort(heroArray, sz);
      
      	//打印排序后所有英雄的信息
      	printInfo(heroArray, sz);
      
      	system("pause");
      	return 0;
      }
      ```

# 一阶段案例：通讯录管理系统

## （一）系统需求

- 利用C++实现一个通讯录管理系统

- 需要实现的功能：

  - 添加联系人：向通讯录中添加新人，新人信息包括（姓名、性别、年龄、联系电话、家庭住址），最多记录1000人

  - 显示联系人：显示通讯录中所有联系人信息

  - 删除联系人：按照姓名进行删除指定联系人

  - 查找联系人：按照姓名查看指定联系人信息

  - 修改联系人：按照姓名重新修改指定联系人

  - 清空联系人：清空通讯录中所有信息
  - 退出通讯录：退出当前使用的通讯录

## （二）创建项目

- 创建一个C++项目（VS2013版本）

  1. 文件→新建→项目→visual C++→空项目     （Ctrl+Shift+N）
  2. 源文件（右键）→添加→新建项→C++文件   （Ctrl+Shift+A）

## （三）菜单功能

- 功能描述：用户选择功能的页面

- ```c++
  void menu()
  {
  	cout << "*************************" << endl;
  	cout << "******	1.添加联系人	******" << endl;
  	cout << "******	2.显示联系人	******" << endl;
  	cout << "******	3.删除联系人	******" << endl;
  	cout << "******	4.查找联系人	******" << endl;
  	cout << "******	5.修改联系人	******" << endl;
  	cout << "******	6.清空联系人	******" << endl;
  	cout << "******	0.退出通讯录	******" << endl;
  	cout << "*************************" << endl;
  }
  ```

## （四）退出功能

- 退出通讯录功能

- 思路：根据用户不同选择，进入不同功能，选择swich结构，选择0时退出

- ```c++
  int select = 0;//存放用户输入的选择
  	
  	while (1)
  	{
  		menu();//调用菜单
  		cin >> select;//用户输入选择
  		switch (select)
  		{
  		case 1:
  			break;//1.添加联系人
  		case 2:
  			break;//2.显示联系人
  		case 3:
  			break;//3.删除联系人	
  		case 4:
  			break;//4.查找联系人
  		case 5:
  			break;//5.修改联系人
  		case 6:
  			break;//6.清空联系人
  		case 0:
  			cout << "欢迎下次使用" << endl;
  			system("pause");//按任意键继续
  			return 0;
  			break;//0.退出通讯录
  		default:
  			break;
  		}
  ```

## （五）添加联系人

- 向通讯录中添加新人，新人信息包括（姓名、性别、年龄、联系电话、家庭住址），最多记录1000人

- 步骤：

  - 设计联系人结构体

    - 信息包括（姓名、性别、年龄、联系电话、家庭住址）

    - ```c++
      //联系人结构体
      struct Person
      {
      	string name;//姓名
      	int sex;//性别
      	int age;//年龄
      	string phone;//电话
      	string addr;//住址
      };
      ```

  - 设计通讯录结构体

    - 通讯录结构体，用于维护一个最大容量为1000人的联系人结构体数组，并记录当前通讯录中联系人数量

    - ```c++
      struct Addressbooks
      {
      	struct Person personArray[MAX];//联系人结构体类型的数组
      	int size;//通讯录中已添加人数
      };
      ```
  
  - main函数中创建通讯录
  
    - 添加联系人函数封装好后，在main函数中创建一个通讯录变量，这个变量就是我们需要一直维护的通讯录
  
    - ```c++
      Addressbooks abs;//创建通讯录结构体变量
      	abs.size = 0;//初始化通讯录中当前人数个数
      ```
  
  - 封装添加联系人功能
  
    - 添加联系人前先判断通讯录是否已满，若满了则不再添加；若未满则将新联系人信息逐个加入通讯录
  
    - ```c++
      //添加联系人
      void addPerson(Addressbooks* abs)
      {
      	//先判断通讯录是否已满
      	if (abs->size == MAX)
      	{
      		cout << "通讯已满，无法添加" << endl;
      		return;
      	}
      	//姓名
      	cout << "请输入姓名" << endl;
      	cin >> abs->personArray[abs->size].name;//这里的访问方式有点疑惑；数组下标即为已有联系人个数
      	//性别
      	cout << "请输入性别" << endl;
      	cout << "1 --- 男" << endl;
      	cout << "2 --- 女" << endl;
      	while (1)//需要循环输入判断，直到输入正确(1或2）
      	{
      		int sex = 0;
      		cin >> sex;
      		if (sex == 1 || sex == 2)
      		{
      			abs->personArray[abs->size].sex = sex;
      			break;
      		}
      		else
      		{
      			cout << "输入有误，请重新输入" << endl;
      		}
      	}
      	//年龄
      	cout << "请输入年龄" << endl;
      	while (1)//需要循环输入判断，直到输入正确(大于0且小于等于150）
      	{
      		int age = 0;
      		cin >> age;
      		if (age > 0 && age <= 150)
      		{
      			abs->personArray[abs->size].age = age;
      			break;
      		}
      		else
      		{
      			cout << "输入有误，请重新输入" << endl;
      		}
      	}
      	//电话
      	cout << "请输入电话" << endl;
      	cin >> abs->personArray[abs->size].phone;
      	//家庭住址
      	cout << "请输入家庭住址" << endl;
      	cin >> abs->personArray[abs->size].addr;
      	abs->size++;	//已有联系人数量加1
      	cout << "添加成功" << endl;
      	system("pause");//请按任意键继续
      	system("cls");//清屏操作
      }
      ```
  
  - 测试添加结构体功能
  
    - ```c++
      case 1:
      			addPerson(&abs);//添加联系人
      			break;
      ```

## （六）显示联系人

- 功能描述：显示通讯录中全部已有联系人信息

- 步骤：

  - 封装显示联系人函数
    - 判断当前通讯录中有没有人员，若人员为0，则提示记录为空；若人数大于0，则显示联系人信息
    
    - ```c++
      void showPerson(Addressbooks* abs)//可以用值传递，但浪费空间，所以用地址传递；是不是用const修饰更好？
      {
      	if (abs->size == 0)
      	{
      		cout << "记录为空" << endl;
      	}
      	for (int i = 0; i < abs->size; i++)
      	{
      		cout << "姓名：" << abs->personArray[i].name << "\t";
      		cout << "性别：" << (abs->personArray[i].sex == 1 ? "男" : "女") << "\t";//使用了一个3目运算符，若为1，则输出男；不为1，则输出女
      		cout << "年龄：" << abs->personArray[i].age << "\t";
      		cout << "电话：" << abs->personArray[i].phone << "\t";
      		cout << "住址：" << abs->personArray[i].addr << "\t";
      	}
      	system("pause");//请按任意键继续
      	system("cls");//清屏操作
      }
      ```
    
  - 测试显示联系人函数

    - ```c++
      case 2:
      			showPerson(&abs);//2.显示联系人
      			break;
      ```

## （七）删除联系人

- 功能描述：按照姓名进行删除指定联系人

- 步骤：

  - 封装检测联系人是否存在（为什么要单独封装一个检测功能？因为这个功能会多个函数经常重复用到）

    - 先判断用户输入的联系人是否存在，如果存在则返回联系人在通讯录的位置；不存在则返回-1

    - 注意："控制传输跳过的实例化"，cese语句中若需要实例化对象，则需要将这段case语句中的代码用大括号括起来

    - ```c++
      //检测联系人是否存在
      int isExist(Addressbooks* abs,string name)
      {
      	for (int i = 0; i < abs->size; i++)
      	{
      		if (abs->personArray[i].name == name)
      		{
      			return i;//找到了，返回联系人数组下标
      		}
      		return -1;//如果遍历结束都没有找到，则返回-1
      	}
      }
      ```

  - 封装删除联系人函数

    - ```c++
      void deletePerson(Addressbooks* abs)
      {
      	cout << "请输入您要删除的联系人" << endl;
      	string name;
      	cin >> name;
      	int ret = isExist(abs, name);//这里的abs已经是指针类型，不需要再取地址
      	if (ret == -1)
      	{
      		cout << "查无此人" << endl;
      	}
      	else
      	{
      		//将要删除联系人后面的联系人信息依次前移，最后联系人数量减一
      		for (int i = ret; i < abs->size; i--)
      		{
      			abs->personArray[i] = abs->personArray[i + 1];//可以直接将整个联系人结构体赋过去
      		}
      		abs->size--;
      		cout << "删除成功" << endl;
      	}
      	system("pause");//请按任意键继续
      	system("cls");//清屏操作
      }
      ```

  - 测试删除联系人功能
  
    - ```c++
      case 3:
      			deletePerson(&abs);//3.删除联系人	
      			break;
      ```

## （八）查找联系人

- 功能描述：按照姓名查找联系人并输出其全部信息

- 步骤：

  - 封装查找联系人函数

    - ```c++
      void findPerson(Addressbooks* abs)
      {
      	cout << "请输入您要查找的联系人" << endl;
      	string name;
      	cin >> name;
      	//检测联系人是否存在
      	int ret = isExist(abs, name);
      	if (ret == -1)
      	{
      		cout << "查无此人" << endl;
      	}
      	else
      	{
      		cout << "找到了该联系人，信息如下：" << endl;
      		cout << "姓名：" << abs->personArray[ret].name << "\t";
      		cout << "性别：" << (abs->personArray[ret].sex == 1 ? "男" : "女") << "\t";//使用了一个3目运算符，若为1，则输出男；不为1，则输出女
      		cout << "年龄：" << abs->personArray[ret].age << "\t";
      		cout << "电话：" << abs->personArray[ret].phone << "\t";
      		cout << "住址：" << abs->personArray[ret].addr << "\t";
      	}
      	system("pause");//请按任意键继续
      	system("cls");//清屏操作
      }
      ```

  - 测试查找联系人功能
  
    - ```c++
      case 4:
      			findPerson(&abs);//4.查找联系人
      			break;
      ```

## （九）修改联系人

- 功能描述：按照姓名重新修改指定联系人

- 步骤：

  - 封装修改联系人函数

    - 查找用户输入的联系人，如果查找成功则进行修改；查找失败则提示查无此人

    - ```c++
      void modifyPerson(Addressbooks* abs)
      {
      	cout << "请输入您要删除的联系人" << endl;
      	string name;
      	cin >> name;
      	//检测联系人是否存在
      	int ret = isExist(abs, name);
      	if (ret == -1)
      	{
      		cout << "查无此人" << endl;
      	}
      	else
      	{
      		//姓名
      		cout << "请输入修改后的姓名" << endl;
      		cin >> abs->personArray[abs->size].name;//这里的访问方式有点疑惑；数组下标即为已有联系人个数
      		//性别
      		cout << "请输入修改后的性别" << endl;
      		cout << "1 --- 男" << endl;
      		cout << "2 --- 女" << endl;
      		while (1)//需要循环输入判断，直到输入正确(1或2）
      		{
      			int sex = 0;
      			cin >> sex;
      			if (sex == 1 || sex == 2)
      			{
      				abs->personArray[abs->size].sex = sex;
      				break;
      			}
      			else
      			{
      				cout << "输入有误，请重新输入" << endl;
      			}
      		}
      		//年龄
      		cout << "请输入修改后的年龄" << endl;
      		while (1)//需要循环输入判断，直到输入正确(大于0且小于等于150）
      		{
      			int age = 0;
      			cin >> age;
      			if (age > 0 && age <= 150)
      			{
      				abs->personArray[abs->size].age = age;
      				break;
      			}
      			else
      			{
      				cout << "输入有误，请重新输入" << endl;
      			}
      		}
      		//电话
      		cout << "请输入修改后的电话" << endl;
      		cin >> abs->personArray[abs->size].phone;
      		//家庭住址
      		cout << "请输入修改后的家庭住址" << endl;
      		cin >> abs->personArray[abs->size].addr;
      	}
      	system("pause");//请按任意键继续
      	system("cls");//清屏操作
      }
      ```

  - 测试修改联系人功能
  
    - ```c++
      case 5:
      			modifyPerson(&abs);//5.修改联系人
      			break;
      ```

## （十）清空联系人

- 功能描述：清空通讯录中所有联系人

- 步骤：

  - 封装清空联系人函数

    - 只需要把通讯录的联系人数量置为0即可，逻辑清空

    - ```c++
      void clearPerson(Addressbooks* abs)
      {
      	abs->size = 0;
      	cout << "通讯录以清空" << endl;
      	system("pause");//请按任意键继续
      	system("cls");//清屏操作
      }
      ```

  - 测试清空联系人功能
  
    - ```c++
      case 6:
      			{
      				cout << "请确认是否要清空全部联系人\n 0 --- 取消\n 1 --- 确认" << endl;
      				int cle = 0;
      				cin >> cle;
      				if (cle == 1)
      				{
      					clearPerson(&abs);//6.清空联系人
      				}
      				else
      				{
      					cout << "欢迎下次使用" << endl;
      					system("pause");//按任意键继续
      				}
      				break;
      			}
      ```

## （十一）完整文件：

- 11.[C++学习一阶段案例：通讯录管理系统.cpp](https://github.com/zzx051900/C-/blob/a39f5c2707dd177f4d6719720c9eadf0d43ca457/C%2B%2B%E7%A8%8B%E5%BA%8F%E7%BB%83%E4%B9%A0%E4%BB%A3%E7%A0%81/11.C%2B%2B%E5%AD%A6%E4%B9%A0%E4%B8%80%E9%98%B6%E6%AE%B5%E6%A1%88%E4%BE%8B%EF%BC%9A%E9%80%9A%E8%AE%AF%E5%BD%95%E7%AE%A1%E7%90%86%E7%B3%BB%E7%BB%9F.cpp)



# 二.C++核心编程

- 本阶段主要针对C++面向对象编程`(Object-Oriented Programming)`技术做详细讲解，探讨C++中的核心精髓
- C++语言能够支持的程序设计范型：
  - 过程程序设计`(Procedural programming)`
  - 模块化程序设计`(Modular programming)`
  - 面向对象程序设计`(Object-oriented programming)`
  - 类属程序设计`(Generic programming)`


## （一）内存分区模型

- 内存四区：
  - C++程序在执行时，将内存大方向划分为四个区域：
    - 代码区：存放函数体的二进制代码，由操作系统进行管理
    - 全局区：存放全局变量和静态变量以及常量
    - 栈区：由编译器自动分配释放，存放函数的参数值，局部变量等
    - 堆区：由程序员分配和释放，若程序员不释放，程序结束时由系统回收
  - 内存四区的意义：不同区域存放的数据，赋予不同的生命周期，给我们更大的灵活编程

###  1.程序运行前

- 在程序编译后，生成了exe可执行程序，未执行前分为两个区域：
  - 代码区：
    - 存放CPU执行的机器指令
    - 代码区是**共享**的，共享的目的是对于频繁被执行的程序，只需要在内存中有一份代码即可
    - 代码区是**只读**的，只读的原因是防止程序意外修改了它的指令
  - 全局区：
    - 全局变量和静态变量存放在此
    - 全局区还包含了常量区、字符串常量和其他常量也存放在此，包括const修饰的全局变量（全局常量）
    - 该区域的数据在程序结束后由操作系统释放
    - 局部变量、const修饰的局部变量（局部常量）都不在全局区

### 2.程序运行后

#### 栈区：

- 由编译器自动分配释放，存放函数的参数值（函数的形参数据），局部变量等

- 注意事项：不要返回局部变量的地址，栈区开辟的数据由编译器自动释放

  - 若返回局部变量的地址，用指针接收，在主函数中解引用输出：
    - 第一次可以正确打印，是因为编译器做了保留
    - 第二次打印这个数据就不再保留，会输出一段随机值

  - 所以不要使用这种操作

- ```c++
  int* func()
  {
      int a = 10;
      return &a;
  }
  int main()
  {
      int *p = func();
      cout << *p << endl;//第一次可以正确打印，是因为编译器做了保留
      cout << *p << endl;//第二次打印这个数据就不再保留，会输出一段随机值
      system("pause");
      return 0;
  }
  ```

#### 堆区：

- 由程序员分配和释放，若程序员不释放，程序结束时由系统回收；在C++中主要利用new在堆区开辟内存

- ```c++
  int* p = new int(10);
  ```

### 3.new操作符

- C++中new操作符在堆区开辟空间

- 堆区开辟的数据，由程序员手动开辟，手动释放，利用操作符delete

  - ```c++
    //释放
    delete p;
    ```

- 语法：`new 数据类型`

- 利用new创建的数据，会返回该数据对应的类型的指针

  - 用new创建一个整形变量

    - ```c++
      int *ptr = new int; // 分配一个 int 大小的内存块，并返回指向该内存块的指针
      int* p = new int(10);//10代表这个整形变量现在赋的初值
      delete ptr;   // 释放单个变量的内存
      ```

  - 用new创建一个整形数组
  
    - ```c++
      int* arr = new int[10];//10代表数组有10个元素
      //释放数组时
      delete[] arr;
      ```
      
    - 要注意的是，使用 `delete` 后，指针变量仍然存在，但指向的内存已经被释放。为了防止出现悬空指针，通常在释放内存后将指针设置为 `nullptr`，如果在 `delete` 操作后不将指针设置为 `nullptr`，那么该指针将成为悬空指针，可能导致程序出现未定义行为。
    
    - `nullptr` 是 C++11 引入的关键字，用于表示空指针。在之前的 C++ 标准中，通常使用 `NULL` 来表示空指针。然而，`nullptr` 具有一些优点，使得它在现代 C++ 中更为推荐：
    
      1. **类型安全：** `nullptr` 是一种特定的空指针类型，它没有整数类型转换的问题，这在一些情况下可以帮助捕获潜在的类型错误
      2. **可读性：** `nullptr` 更直观，更容易理解。它明确表示空指针，而不会引起与整数 `0` 混淆的问题
      3. **一致性：** 在现代 C++ 中，推荐使用 `nullptr` 来表示空指针，以保持代码的一致性。`nullptr` 更符合 C++11 及以后标准的设计理念

## （二）引用`(references)`

###  1.引用的基本使用

- 作用：给变量起别名

- 语法：`数据类型 &别名 = 原名`

- 示例：

  - ```c++
    int a = 10;
    int &b = a;
    cout << a << endl;
    cout << b << endl;
    b = 20;
    cout << a << endl;
    cout << b << endl;
    ```

###  2.引用注意事项

- 引用必须初始化

- 引用在初始化之后，不可以改变

- 示例：

  - ```c++
    int a = 10;
    int &b = a;
    cout << "a = " << a << endl;
    cout << "b = " << b << endl;
    //int &b;//非法，“需要初始值设定项”
    int c = 20;
    //int &b = c;//非法，“多次初始化”
    b = c;//同时将a的值也改变了，所以引用在初始化后不可以改变
    cout << "a = " << a << endl;
    cout << "b = " << b << endl;
    cout << "c = " << c << endl;
    ```

###  3.引用作函数参数

- 作用：函数传参时，可以用引用的技术让形参修饰实参

- 优点：可以简化指针修改实参

- 示例：

  - ```c++
    void swap(int &a, int &b)
    {
    	int temp = a;
    	a = b;
    	b = temp;
    }
    
    int main()
    {
    	int a = 10;
    	int b = 20;
    	swap(a, b);
    	cout << "a = " << a << endl;//20
    	cout << "b = " << b << endl;//10
    	system("pause");
    	return 0;
    }
    ```

- 总结：通过引用参数产生的效果和按地址传递是一样的，引用的语法更简单

###  4.引用作函数返回值

- 引用是可以作为函数的返回值的

- 注意：不要返回局部变量引用

  - 类似于不要返回局部变量的地址

- 用法：函数调用作为左值

  - ```c++
    int& test()
    {
    	static int a = 10;0
    	return a;
    }
    
    int main()
    {
    	int &ref = test();
    	cout << "ref = " << ref << endl;
    	cout << "ref = " << ref << endl;
    	test() = 100;//相当于"a = 100"
    	cout << "ref = " << ref << endl;
    	system("pause");
    	return 0;
    }
    ```

###  5.引用的本质

- 本质：引用的本质在C++内部实现是一个**指针常量**

- ```c++
  //发现是引用，转换为 int* const ref = &a;
  void func(int& ref)
  {
  	ref = 100;// ref是引用，转换为 *ref = 100
  }
  
  int main()
  {
  	
  	int a = 10;
  	int &ref = a;//自动转换为 int * const ref = &a;指针常量是指针指向不可更改(但指针指向内存空间的值可以更改），也说明了引用为什么不可以更改
  	ref = 20;//内部发现ref是引用，自动转换为：*ref = 20;
  	cout << "a = " << a << endl;
  	cout << "ref = " << ref << endl;
  	system("pause");
  	return 0;
  }
  ```

- 总结：C++推荐用引用技术，因为语法方便，引用本质是指针常量，但是所有的指针操作编译器都帮我们做了

###  6.常量引用

- 作用：常量引用主要用来修饰形参，防止误操作

  - 在函数形参列表中，可以加const修饰形参，防止形参改变实参

  - ```c++
    int a = 10;
    int &ref = 10;//非法的，引用必须引一块合法的内存空间
    const int &ref = 10;//合法，因为加上const后，编译器会将这句代码改为int temp = 10;const int &ref = temp;
    //加入const后变为只读，不可以修改	
    ```

## （三）函数提高

###  1.函数的默认参数

- 在C++中，函数的形参是可以有默认值的

- 语法：`返回值类型 函数名(参数 = 默认值)`

- 注意：

  - 如果我们自己传入数据，就用自己的数据，如果没有，就用默认值

  - 如果某个位置已经有了默认参数，那么从这个位置从左向右都必须有默认值

    - ```c++
      //错误案例:
      int func(int a, int b = 20, int c)
      {
      	return a + b + c;
      }
      ```

  - 如果函数声明有默认参数，函数实现不能有默认参数（声明和实现只能有一个默认参数）

    - ```c++
      //错误案例：
      //函数声明
      int func(int a = 10,int b = 20);
      //函数实现
      int func(int a = 10,int b = 20)
      {
          return a + b;
      }
      //报错：重定义默认参数
      
      
      //正确写法
      int func(int a, int b)
      {
      	return a + b;
      }
      ```

- 示例：

  - ```c++
    //如果我们自己传入数据，就用自己的数据，如果没有，就用默认值
    int func(int a, int b = 20, int c = 30)
    {
    	return a + b + c;
    }
    int main()
    {
    	cout << func(10) << endl;//60
    	cout << func(10, 30) << endl;//70
    	
    	system("pause");
    	return 0;
    }
    ```

###  2.函数的占位参数

- C++中函数的形参列表可以有占位参数，用来作占位，调用函数时必须填补该位置

- 语法：`返回值类型 函数名(数据类型)`

- 占位参数，还可以有默认参数

- 示例：

- ```c++
  void func(int a, int)
  {
  	cout << "func" << endl;
  }
  
  int main()
  {
  	func(10,20);
  
  	system("pause");
  	return 0;
  }
  ```

###  3.函数重载

#### （1）概述：

- 作用：函数名可以相同，提高复用性

- 函数重载满足条件：

  - 同一个作用域下
  - 函数名称相同
  - 函数参数类型不同，或者个数不同，或者顺序不同

- 注意：函数的返回值不可以作为函数重载的条件（无法重载只按返回值类型区分的函数）

- 示例：

  - ```c++
    void func()
    {
    	cout << "func的调用1" << endl;
    }
    void func(int a)
    {
    	cout << "func的调用2" << endl;
    }
    void func(double a)
    {
    	cout << "func的调用3" << endl;
    }
    void func(int a, double b)
    {
    	cout << "func的调用4" << endl;
    }
    void func(double a, int b)
    {
    	cout << "func的调用5" << endl;
    }
    
    int main()
    {
    	func();
    	func(10);
    	func(3.14);
    	func(10, 3.14);
    	func(3.14, 10);
    
    	system("pause");
    	return 0;
    }
    ```

#### （2）函数重载注意事项

- 引用作为重载条件

  - ```c++
    void func(int &a)
    {
    	cout << "func(int &a)的调用" << endl;
    }
    void func(const int &a)
    {
    	cout << "func(const int &a)的调用" << endl;
    }
    
    int main()
    {
    	int a = 10;
    	func(a);
    	func(10);//int &a = 10;不合法   但const int &a = 10;合法
    	
    	system("pause");
    	return 0;
    }
    ```

- 函数重载遇到函数默认参数

  - ```c++
    void func(int a)
    {
    	cout << "func(int a)的调用" << endl;
    }
    void func(int a, int b = 10)
    {
    	cout << "func(int a,int b = 10)的调用" << endl;
    }
    
    int main()
    {
    	
    	func(10);//报错；当函数重载碰到默认参数，可能出现二义性报错，要尽量避免
    	func(10, 20);//正常运行
    	
    	system("pause");
    	return 0;
    }
    ```

## （四）类和对象

- C++面向对象三大特性：封装、继承、多态
- C++认为万事万物都皆为对象，对象上有其属性和行为
  - 人可以作为对象
    - 属性：姓名、年龄、身高、体重...
    - 行为：走、跑、跳、吃饭、唱歌
  - 车可以作为对象
    - 属性：轮胎、方向盘、车灯...
    - 行为：载人、放音乐、用空调
- 具有相同性质的对象，我们可以将其抽象为类，人属于人类、车属于车类

### 1.封装`(encapsulation)`

#### （1）封装的意义

- 封装的意义：

  1. 将属性和行为作为一个整体，表现生活中的事物

  2. 将属性和行为加以权限控制
     - 可以在成员函数内判断数据的有效性
  

##### 封装的意义1：

  - 在设计类的时候，将属性和行为作为一个整体，表现生活中的事物

  - 语法：

    - ```c++
      class 类名
      { 
          访问权限：
          属性:
          行为（函数）:
      };
      ```

    - 类中的属性和行为，统一称为**成员**

    - 属性，也称为成员属性、成员变量

    - 行为，也称为成员函数，成员方法

  - 示例1：设计一个圆类，求圆的周长

    - ```c++
      #include<iostream>
      #include<string>
      using namespace std;
      
      //设计一个圆类，求圆的周长
      
      const double PI = 3.14;//圆周率
      
      class Circle	//定义圆类
      {
      	//访问权限:
      	//公共权限
      public:
      
      	//属性:
      	int m_r;//半径
      
      	//行为（函数）:
      	double calculateZC()//计算圆的周长
      	{
      		return 2 * PI * m_r;
      	}
      };
      
      int main()
      {	
      	Circle c1;//通过圆类，创建（实例化）一个具体的圆（对象）
      	c1.m_r = 10;//给圆对象的属性赋值，半径赋值10
      	cout << "圆的周长为" << c1.calculateZC() << endl;//调用类的行为（函数）
      
      	system("pause");
      	return 0;
      }
      ```

  - 示例2：设计一个学生类，属性有姓名和学号，可以给姓名和学号赋值，可以显示学生的姓名和学号

    - ```c++
      #include<iostream>
      #include<string>
      using namespace std;
      //学生类
      class Student
      {
      //访问权限
      public:	//公共权限
      	//属性:
      	string m_Name;//姓名
      	int m_Id;//学号
      	//行为：
      	//展示学号和姓名
      	void showStudent()
      	{
      		cout << "姓名：" << m_Name << " 学号：" << m_Id << endl;
      	}
      	//给姓名赋值
      	void setName(string name)
      	{
      		m_Name = name;
      	}
      	//给学号赋值
      	void setId(int id)
      	{
      		m_Id = id;
      	}
      };
      int main()
      {
      	//创建一个具体的学生（实例化）
      	Student s1;
      	//s1进行属性赋值
      	s1.m_Id = 1;
      	s1.m_Name = "aaa";
      	//显示学生信息
      	s1.showStudent();
      	//将s1的名字和学号更改
      	s1.setName("bbb");
      	s1.setId(2);
      	s1.showStudent();
      	system("pause");
      	return 0;
      }
      ```

##### 封装的意义2（访问权限）：

- 类在设计时，可以0

- 

- 把属性和行为放在不同的权限下，加以控制

- 访问权限有三种：

  - 公共权限：public（成员类内可以访问，类外可以访问）
  - 保护权限：protected（成员类内可以访问，类外不可以访问（儿子可以访问父亲中的保护内容））
  - 私有权限：private（成员类内可以访问，类外不可以访问（儿子不可以访问父亲中的隐私内容））
    - 如果在类中声明成员而没有指定访问权限，则默认为私有成员。私有成员只能在类的内部访问，外部代码无法直接访问私有成员

- 示例：

  - ```c++
    #include<iostream>
    #include<string>
    using namespace std;
    class Person
    {
    public:	//公共权限
    	string m_Name;//姓名
    protected:	//保护权限
    	string m_Car;//汽车
    private:	//私有权限
    	string m_Password;//个人密码
    public:
    	void func()
    	{
    		m_Name = "aaa";
    		m_Car = "拖拉机";
    		m_Password = "123456";
    		//三种权限都可在类内正常访问
    	}		
    };
    int main()
    {
    	Person p1;
    	p1.m_Name = "bbb";
    	//p1.m_Car = "自行车";//保护权限，类外不可访问（报错：成员已声明，不可访问。）
    	//p1.m_Password = "111111";//私有权限，类外不可访问（报错：成员已声明，不可访问。）
    
    	system("pause");
    	return 0;
    }
    ```


####  （2）struct和class的区别

- 在C++中`struct`和`class`唯一的区别就在于**默认的访问权限不同**

- 区别：

  - `struct`默认权限为公共
  - `class`默认权限为私有

- ```c++
  class C1
  {
  	int m_A;	//默认权限为私有
  };
  struct C2
  {
  	int m_A;	//默认权限为公共
  };
  int main()
  {
  	C1 c1;
  	//c1.m_A = 100;//报错；因为私有变量在类外不可以访问
  	C2 c2;
  	c2.m_A = 100;//正常
  	system("pause");
  	return 0;
  }
  ```

#### （3）成员属性设置为私有

- 成员设置为私有的优点：

  1. 将所有成员设置为私有，可以自己控制读写权限
  2. 对于写权限，我们可以检测数据的有效性

#### （4）封装的练习案例

- 练习案例1：设计立方体类
  - 设计立方体类（Cube），求出立方体的面积和体积，分别用全局函数和成员函数判断两个立方体是否相等
  
  - 文件：[12.类和对象案例1-立方体类.cpp](https://github.com/zzx051900/C-/blob/31c167785496f83ed042722763a65d9185fce9b3/C%2B%2B%E7%A8%8B%E5%BA%8F%E7%BB%83%E4%B9%A0%E4%BB%A3%E7%A0%81/12.%E7%B1%BB%E5%92%8C%E5%AF%B9%E8%B1%A1%E6%A1%88%E4%BE%8B1-%E7%AB%8B%E6%96%B9%E4%BD%93%E7%B1%BB.cpp)
  
    - 代码：
  
      - ```c++
        //(未完善）
        #include<iostream>
        using namespace std;
        
        /*
        立方体类设计：
        1.创建立方体类
        2.设计属性
        3.设计行为：获取立方体面积和体积
        4.分别用全局函数和成员函数判断两个立方体是否相等
        */
        
        class Cube
        {
        public:
        	//设置长
        	void setL(int l)
        	{
        		m_L = l;
        	}
        	//获取长
        	int getL()
        	{
        		return m_L;
        	}
        	//设置宽
        	void setW(int w)
        	{
        		m_W = w;
        	}
        	//获取宽
        	int getW()
        	{
        		return m_W;
        	}
        	//设置高
        	void setH(int h)
        	{
        		m_H = h;
        	}
        	//获取高
        	int getH()
        	{
        		return m_H;
        	}
        	//获取立方体面积
        	int calculateS()
        	{
        		return 2 * (m_L*m_W + m_L*m_H + m_W*m_H);
        	}
        	//获取立方体体积
        	int calculateV()
        	{
        		return m_L * m_W * m_H;
        	}
        	//利用成员函数判断两个立方体是否相等（此时参数只传一个，因为又另一个立方体调用的这个成员函数，不需要传参）
        	bool isSameByClass(Cube &c)
        	{
        		//判断条件
        		//m_L   
        		//c2.getL()
        		return 1;
        	}
        
        private:
        	int m_L;//长
        	int m_W;//宽
        	int m_H;//高
        };
        
        bool isSame(Cube &c1, Cube &c2);
        
        int main()
        {
        	//创建一个立方体对象
        	Cube c1;
        	c1.setL(10);//长设为10
        	c1.setW(10);
        	c1.setH(10);
        
        	cout << "c1的面积为：" << c1.calculateS() << endl;
        	cout << "c1的体积为：" << c1.calculateV() << endl;
        
        	//创建第二个立方体
        	Cube c2;
        	c2.setL(10);//长设为10
        	c2.setW(10);
        	c2.setH(10);
        
        	//利用全局函数判断
        	bool ret = isSame(c1, c2);
        	if (ret)
        	{
        		cout << "全局函数判断相等" << endl;
        	}
        	else
        	{
        		cout << "全局函数判断不相等" << endl;
        	}
        
        	//利用成员函数判断
        	ret = c1.isSameByClass(c2);
        	if (ret)
        	{
        		cout << "成员函数判断相等" << endl;
        	}
        	else
        	{
        		cout << "成员函数判断不相等" << endl;
        	}
        
        	system("pause");
        	return 0;
        }
        
        //利用全局函数判断两个立方体是否相等
        bool isSame(Cube &c1, Cube &c2)
        {
        	//判断条件
        	return 1;
        }
        ```
  
- 练习案例2：点和圆的关系
  - 设计一个圆形类和一个点类，计算点和圆的关系
  
  - 文件：
    - [13.类和对象案例2-点和圆关系](https://github.com/zzx051900/C-/tree/31c167785496f83ed042722763a65d9185fce9b3/C%2B%2B%E7%A8%8B%E5%BA%8F%E7%BB%83%E4%B9%A0%E4%BB%A3%E7%A0%81/13.%E7%B1%BB%E5%92%8C%E5%AF%B9%E8%B1%A1%E6%A1%88%E4%BE%8B2-%E7%82%B9%E5%92%8C%E5%9C%86%E5%85%B3%E7%B3%BB)
      
      - 13.类和对象案例2-点和圆关系.cpp
      
        - ```c++
          #include<iostream>
          #include"point.h"
          #include"circle.h"
          
          using namespace std;
          
          //函数声明
          void isInCircle(Circle &c, Point &p);
          
          int main()
          {
          	Circle c;//创建一个圆
          	c.setR(10);//设置圆的半径
          	Point center;//创建圆的圆心
          	center.setX(10);//设置圆心的x
          	center.setY(0);//设置圆心的y
          	c.setCenter(center);//设置圆心
          	Point p;//创建点
          	p.setX(10);//设置点的x
          	p.setY(5);//设置点的y
          	//p.setY(10);
          	//p.setY(15);
          
          	isInCircle(c, p);
          
          	system("pause");
          	return 0;
          }
          
          //判断点和圆的关系
          void isInCircle(Circle &c, Point &p)
          {
          	//计算两点间距离的平方
          	int distance = (c.getCenter().getX() - p.getX())*(c.getCenter().getX() - p.getX()) +
          		(c.getCenter().getY() - p.getY())*(c.getCenter().getY() - p.getY());
          	//计算半径的平方
          	int rDistance = c.getR() * c.getR();
          	if (distance == rDistance)
          	{
          		cout << "点在圆上" << endl;
          	}
          	else if (distance > rDistance)
          	{
          		cout << "点在圆外" << endl;
          	}
          	else
          	{
          		cout << "点在圆内" << endl;
          	}
          }
          ```
      
      - point.h
      
        - ```c++
          #pragma once//防止头文件重复包含
          #include<iostream>
          using namespace std;
          
          //
          
          //设计点类
          class Point
          {
          public:
          	//设置x
          	void setX(int x);
          
          	//获取x
          	int getX();
          
          	//设置y
          	void setY(int y);
          
          	//获取y
          	int getY();
          
          
          private:
          	int m_X;//x坐标
          	int m_Y;//y坐标
          };
          ```
      
      - point.cpp
      
        - ```c++
          #include"point.h"
          //设计点类
          
          
          //设置x
          void Point::setX(int x)
          {
          	m_X = x;
          }
          //获取x
          int Point::getX()
          {
          	return m_X;
          }
          //设置y
          void Point::setY(int y)
          {
          	m_Y = y;
          }
          //获取y
          int Point::getY()
          {
          	return m_Y;
          }
          ```
      
      - circle.h
      
        - ```c++
          #pragma once
          #include<iostream>
          #include"point.h"
          using namespace std;
          
          //设计圆类
          class Circle
          {
          public:
          	//设置半径
          	void setR(int r);
          	
          	//获取半径
          	int getR();
          	
          	//设置圆心
          	void setCenter(Point center);
          	
          	//获取圆心
          	Point getCenter();
          	
          private:
          	int m_R;//半径
          	//在类中，可以让另一个类的作为本类中的成员
          	Point m_Center;//圆心
          };
          ```
      
      - crecle.cpp
      
        - ```c++
          #include"circle.h"
          
          
          //ÉèÖÃ°ë¾¶
          void Circle::setR(int r)
          {
          	m_R = r;
          }
          //»ñÈ¡°ë¾¶
          int Circle::getR()
          {
          	return m_R;
          }
          //ÉèÖÃÔ²ÐÄ
          void Circle::setCenter(Point center)
          {
          	m_Center = center;
          }
          //»ñÈ¡Ô²ÐÄ
          Point Circle::getCenter()
          {
          	return m_Center;
          }
          ```
    
  - 在类中，可以让另一个类的作为本类中的成员
  
  - 初步学习将一个大型文件拆分为多个文件
    - 头文件需要添加：`#pragma once//防止头文件重复包含`
    - 将多个类分别创建头文件和cpp文件保存，头文件中的成员函数只保留声明，实现在cpp文件中
    - 主文件中要包含其他所有头文件

### 2.对象的初始化和清理

- 生活中我们买的电子产品基本都有出厂设置，在某一天我们不用时也会删除一些自己的信息数据保证安全

- C++的面向对象来源于生活，每个对象也都会有初始设置以及对象销毁前的清理数据的设置

#### （1）构造函数`(constructor)`和析构函数

##### 引言：

- 对象的初始化和清理是两个非常重要的安全问题
  - 一个对象或变量没有初始状态，对其使用后果是未知
  - 同样的，使用完一个对象或变量，没有及时清理，也会造成一定的安全问题
- C++利用了**构造函数**（用于初始化）和**析构函数**（用于清理）解决上述问题，这两个函数会被编译器自动调用，完成对象初始化和清理工作，对象的初始化和清理是编译器强制我们要做的事，因此如果我们不提供构造和析构，编译器会自动提供，但编译器提供的构造函数和析构函数是空实现

##### 构造函数：

- 构造函数：主要作用在于创建对象时为对象的成员属性赋值，构造函数由编译器自动调用，无需手动调用

- 语法：`类名(){}`
  1. 构造函数，没有返回值，也不写void
  2. 函数名称与类名相同
  3. 构造函数可以有参数，因此可以发生重载
  4. 程序在调用对象时会自动调用构造，无需手动调用，而且只会调用一次
##### 析构函数：

- 析构函数：主要作用在于对象销毁前系统自动调用，执行一些清理工作
- 语法：`~类名(){}`
    - 析构函数，没有返回值，不写void
    - 函数名称与类名相同，在名称前加上符号~
    - 析构函数不可以有参数，因此不可以发生重载
    - 程序在对象销毁前会自动调用析构，无需手动调用，而且只会调用一次

- 构造函数和析构函数的使用示例：

  - ```c++
    #include<iostream>
    using namespace std;
    //对象的初始化和清理
    class Person
    {
    public:
    	//1.构造函数，进行初始化操作
    	Person()//构造函数会被自动调用
    	{
    		cout << "Person构造函数的调用" << endl;
    	}
    	//2.析构函数
    	~Person()//在对象销毁前，析构函数会被自动调用
    	{
    		cout << "Person析构函数的调用" << endl;
    	}
    };
    void test01()
    {
    	Person p;	//在栈上的数据，函数调用完后被释放，所以析构会执行
    }
    int main()
    {
    	test01();
    	Person p;//不会被释放，所以析构不会执行
    	system("pause");
    	return 0;
    }
    ```


#### （2）构造函数的分类及调用

- 两种分类方式：

  - 按参数分：有参构造和无参构造
  - 按类型分：普通构造和拷贝构造

- 三种调用方式：

  1. 括号法
     - 注意事项：
       - 调用默认构造函数时，不要加括号：因为`Person p1();`这样的代码编译器会认为这是一个函数的声明，不会再创建对象

  2. 显示法
     - 注意事项：
       - 不要利用拷贝构造函数来初始化匿名对象，例：`Person(p2);`，因为编译器会认为其是一个对象声明

  3. 隐式转换法

- 构造函数的分类和具体调用示例：

  - ```c++
    #include<iostream>
    using namespace std;
    class Person
    {
    public:
    	//构造函数：
    	//无参（默认构造default constructor）
    	Person()
    	{
    		cout << "Person无参构造函数的调用" << endl;
    	}
    	//有参
    	Person(int a)
    	{
    		cout << "Person有参构造函数的调用" << endl;
    	}
    	//拷贝构造函数
    	Person(const Person &p) //有疑问
    	{
    		cout << "Person拷贝构造函数的调用" << endl;
    		//将传入对象的属性全部复制到新建对象身上
    	}
    
    	//析构函数
    	~Person()
    	{
    		cout << "Person析构函数的调用" << endl;
    	}
    };
    //3种调用方法
    void test01()
    {
    	//1.括号法
    	Person p1;		//默认构造函数调用
    	Person p2(10);	//有参构造函数调用
    	Person p3(p2);	//拷贝构造函数调用
        	//注意1：
        	//调用默认构造函数时，不要加括号：因为Person p1();这样的代码编译器会认为这是一个函数的声明，不会再创建对象
    	//2.显式法
    	Person p4;
    	Person p5 = Person(10);	//有参	
        	//Person(10);叫做匿名对象。 特点：当前行执行结束后，系统会立即自动回收掉匿名对象
        	//注意2：不要利用拷贝构造函数来初始化匿名对象，例：Person(p2);，因为编译器会认为其是一个对象声明
    	Person p6 = Person(p5);	//拷贝
    	//3.隐式转换法
    	Person p7 = 10;	//相当于 Person p7 = Person(10);	有参构造
    	Person p8 = p7;	//拷贝
    }
    int main()
    {
    	test01();
    
    	system("pause");
    	return 0;
    }
    ```
  
- 其他示例：

  - ```c++
    #include<iostream>
    #include<string>
    using namespace std;
    
    class A
    {
    public:
    	A()
    	{
    		cout << "A的默认构造" << endl;
    	}
    	A(int a)
    	{
    		cout << "A的有参构造" << endl;
    	}
    };
    
    int main()
    {
    	A a1[2];	//两个元素的数组，所以默认构造两次
    
    	A a2[2] = { 5, 10 };	//有参构造两次
    
    	A *p = new A[2];	//默认构造两次
    
    	system("pause");
    	return 0;
    }
    ```



#### （3）拷贝函数调用时机

- C++种拷贝构造函数调用时机通常有三种情况：

  - 使用一个已经创建完毕的对象来初始化一个新对象
  - 值传递的方式给函数参数传值（系统自动调用）
  - 以值方式返回局部对象（系统自动调用）

- 拷贝函数调用时机示例：

  - ```c++
    #include<iostream>
    using namespace std;
    class Person
    {
    public:	
    	Person()	//无参构造
    	{
    		cout << "Person默认构造函数的调用" << endl;
    	}
    	Person(int age)	//有参构造
    	{
    		cout << "Person有参构造函数的调用" << endl;
    		m_Age = age;
    	}
    	Person(const Person &p)	//拷贝构造
    	{
    		cout << "Person拷贝构造函数的调用" << endl;
    		m_Age = p.m_Age;
    	}
    	~Person()	//析构
    	{
    		cout << "Person析构函数的调用" << endl;
    	}
    	int m_Age;
    };
    //C++种拷贝构造函数调用时机通常有三种情况：
    
    //1.使用一个已经创建完毕的对象来初始化一个新对象
    void test01()
    {
    	Person p1(20);	//括号法有参构造函数调用
    	Person p2(p1);	//括号法拷贝构造函数调用
    
    	cout << "p2的年龄:" << p2.m_Age << endl;	//拷贝成功
    }
    //2.值传递的方式给函数参数传值
    void doWork1(Person p)
    {
    }
    void test02()
    {
    	Person p3;	//默认构造函数调用
    	doWork1(p3);	
    }
    //3.以值方式返回局部对象
    Person doWork2()
    {
    	Person p4;	//此时调用默认构造
    	cout << (int*)&p4 << endl;	//输出局部变量的地址，用于观察返回的局部变量是否是用一个变量
    	return p4;	//此时调用拷贝构造
    }
    void test03()
    {
    	Person p = doWork2();
    	cout << (int*)&p << endl;	//与上面局部变量的地址不一致，说明不是同一个变量，是拷贝出来的
    }
    int main()
    {
    	test01();
    	test02();
    	test03();
    	system("pause");
    	return 0;
    }
    ```


#### （4）构造函数调用规则

- 默认情况下：C++编译器至少给一个类添加3个函数：
  - 默认构造函数（无参，函数体为空）
  - 默认析构函数（无参，函数体为空）
  - 默认拷贝构造函数，对属性进行拷贝

- 构造函数调用规则：
  - 如果用户定义有参构造函数，C++不再提供默认构造函数，但是会提供拷贝构造函数
  - 如果用户定义拷贝构造函数，C++不会提供其他构造函数

- 注意：
  
  - 编译器不会默认提供有参构造！！！

- 构造函数调用规则示例：

  - ```c++
    #include<iostream>
    using namespace std;
    class Person
    {
    public:
    	Person()	//无参构造
    	{
    		cout << "Person默认构造函数的调用" << endl;
    	}
    	Person(int age)	//有参构造
    	{
    		cout << "Person有参构造函数的调用" << endl;
    		m_Age = age;
    	}
    	Person(const Person &p)	//拷贝构造
    	{
    		cout << "person拷贝构造函数的调用" << endl;
    		m_Age = p.m_Age;
    	}
    	~Person()	//析构
    	{
    		cout << "Person析构函数的调用" << endl;
    	}
    	int m_Age;
    };
    
    void test01()
    {
    	Person p1;	//括号法无参构造调用 //此时若只把无参构造注释（删除）掉，报错"没有合适的默认构造函数可用"。验证了调用规则1：如果用户定义有参构造函数，C++不再提供默认构造函数
    	
    	p1.m_Age = 18;
    	Person p2(p1);	//括号法拷贝构造调用 //此时如果把拷贝构造函数注释（删除）掉，p2仍然可以正常初始化 
    
    	cout << "p2的年龄:" << p2.m_Age << endl;	//拷贝成功
    }
    
    void test02()
    {
    	Person p3(28);	//括号法有参构造调用 //此时若只把有参构造函数注释掉（删除）掉，报错。验证了调用规则2：如果用户定义拷贝构造函数，C++不会提供其他构造函数
    
    	Person p4(p3);	//括号法拷贝构造调用 //此时如果只把拷贝构造函数注释（删除）掉，p4仍然可以正常初始化 。验证调用规则1：- 如果用户定义有参构造函数，C++还是会提供拷贝构造函数
    
    	cout << "p4的年龄:" << p4.m_Age << endl;	//拷贝成功
    }
    
    int main()
    {
    	test01();
    
    	test02();
    	
    	system("pause");
    	return 0;
    }
    ```


#### （5）深拷贝与浅拷贝

- 浅拷贝：简单的赋值拷贝操作

  - 若使用浅拷贝，且在堆区有申请空间，则析构释放时有可能将同一块空间释放两次导致报错

- 深拷贝：在堆区重新申请空间，进行拷贝操作
- 浅拷贝与深拷贝使用示例：

  - ```c++
    #include<iostream>
    using namespace std;
    class Person
    {
    public:
    	Person()	//无参构造
    	{
    		cout << "Person默认构造函数的调用" << endl;
    	}
    	Person(int age , int height)	//有参构造
    	{
    		cout << "Person有参构造函数的调用" << endl;
    		m_Age = age;
    		m_Height = new int(height);	//堆区开辟空间
    	}
    	~Person()	//析构
    	{
    		//析构代码，用于将堆区开辟的数据释放
    		if (m_Height)
    		{
    			delete m_Height;
    			m_Height = NULL;
    		}
    		cout << "Person析构函数的调用" << endl;
    	}
    	//自己实现拷贝构造函数，解决浅拷贝带来的问题
    	Person(const Person &p)
    	{
    		cout << "Person拷贝构造函数的调用" << endl;
    		m_Age = p.m_Age;
    		//m_Height = p.m_Height;	//这是编译器默认实现的拷贝构造函数
    		m_Height = new int(*p.m_Height);		//深拷贝操作，在堆区新建一块内存
    	}
    
    	int m_Age;
    	int* m_Height;	//用指针是为了创建在堆区
    };
    void test01()
    {
    	Person p1(18, 160);
    	cout << "p1的年龄：" << p1.m_Age << "身高为：" << *p1.m_Height << endl;
    
    	Person p2(p1);
    	cout << "p2的年龄：" << p2.m_Age << " 身高为：" << *p2.m_Height << endl;	//编译器自动做了浅拷贝（简单的赋值拷贝操作）
    }
    int main()
    {
    	test01();
    	system("pause");
    	return 0;
    }
    ```

- 总结：如果属性在堆区有开辟空间，一定要自己提供构造函数，防止浅拷贝带来的问题

#### （6）初始化列表

- 作用：C++提供了初始化列表操作，用来初始化属性

- 语法：`构造函数():属性1(值1),属性2(值2)...{}`

- 初始化列表示例：

  - ```c++
    #include<iostream>
    using namespace std;
    class Person
    {
    public:
    	//传统初始化操作
    	Person(int a, int b, int c)
    	{
    		m_A = a;
    		m_B = b;
    		m_C = c;
    	}
    	//初始化列表
    	Person() :m_A(10), m_B(20), m_C(30) {}
    	//实际使用初始化列表
    	Person(int a, int b, int c) :m_A(a), m_B(b), m_C(c) {}
    
    	int m_A;
    	int m_B;
    	int m_C;
    };
    void test01()
    {
    	Person p(10, 20, 30);
    	//Person p;
    	cout << "m_A = " << p.m_A << endl;
    	cout << "m_B = " << p.m_B << endl;
    	cout << "m_C = " << p.m_C << endl;
    }
    int main()
    {
    	test01();
    	system("pause");
    	return 0;
    }
    ```


#### （7）类对象作为类成员

- C++类中的成员可以是另一个成员类的对象，我们称该成员为对象成员

- 例如：

  - ```c++
    class A {}
    class B
    {
        A a;
    }
    ```

  - B类中有对象A作为成员，A为对象成员

    - ```c++
      #include<iostream>
      #include<string>
      using namespace std;
      class Phone	//手机类
      {
      public:
      	Phone(string pName)	//Phone的有参构造函数
      	{
      		m_PName = pName;
      		cout << "Phone的构造函数调用" << endl;
      	}
      	~Phone()
      	{
      		cout << "Phone的析构函数调用" << endl;
      	}
      	string m_PName;	//手机名
      };
      
      class Person
      {
      public:
      	//使用初始化列表
      	Person(string name, string pName) :m_Name(name), m_Phone(pName)	//隐式转换：Phone m_Phone = pName;
      	{
      		cout << "Person的构造函数调用" << endl;
      	}
      	~Person()
      	{
      		cout << "Person的析构函数调用" << endl;
      	}
      	string m_Name;	//姓名
      	Phone m_Phone;	//手机
      };
      
      void test01()
      {
      	Person p("aaa", "ppp");
      	cout << p.m_Name << "拿着" << p.m_Phone.m_PName  << "手机" << endl;
      }
      
      int main()
      {
      	test01();
      
      	system("pause");
      	return 0;
      }
      ```

      - 当其他类对象作为本类成员时，构造时先构造类对象，后构造自身
      - 析构时顺序与构造相反，可能因为是栈结构


#### （8）静态成员

- 静态成员就是在成员变量和成员函数前加上关键字`static`，称为静态成员

- 静态成员分为：
  - **静态成员变量**：
  
    - 所有对象共享同一份数据，因此静态成员有两种访问方式：
      1. 通过对象进行访问
      2. 通过类名进行访问
    - 在编译阶段分配内存
    - 类内声明，类外初始化
  
  - 静态成员变量示例：
  
    - ```c++
      #include<iostream>
      #include<string>
      using namespace std;
      
      class Person
      {
      public:
      	Person() 
      	{
      		cout << "Person的构造函数调用" << endl;
      	}
      	static int m_A;
      	//静态成员变量也是有访问权限的
      private:
      	static int m_B;
      };
      int Person::m_A = 100;	//静态成员变量，类内声明，类外初始化
      int Person::m_B = 200;
      void test01()
      {
      	Person p;
      	cout << p.m_A << endl;	//若未进行类外的初始化，则报错：无法解析的外部命令
      	Person p2;
      	p2.m_A = 200;
      	//使用另一个类对象修改成员变量
      	cout << p.m_A << endl;	//静态成员变量，所有对象共享一份数据
      }
      void test02()
      {
      	//静态成员变量，不属于某个对象，所有对象共享一份数据
      	//所有对象共享同一份数据，因此静态成员有两种访问方式：
      	//1.通过对象进行访问
      	Person p;
      	cout << p.m_A << endl;
      	//2.通过类名进行访问
      	cout << Person::m_A << endl;
      	//cout << Person::m_B << endl;	//类外访问不到私有静态成员变量
      }
      int main()
      {
      	test01();
      
      	test02();
      	system("pause");
      	return 0;
      }
      ```
  
  - **静态成员函数**
  
    - 所有对象共享同一个函数，也有两种访问方式：
      1. 通过对象进行访问
      2. 通过类名进行访问
    - 静态成员函数只能访问静态成员变量，静态成员函数不可以访问非静态成员变量，因为无法区分到底是哪个对象的非静态成员变量
  
  - 静态成员函数示例：
  
    - ```c++
      #include<iostream>
      #include<string>
      using namespace std;
      
      class Person
      {
      public:
      	//静态成员函数
      	static void func()
      	{
      		m_A = 100;	//静态成员函数可以访问静态成员变量
      		//m_B = 200;	//静态成员函数不可以访问非静态成员变量
      		cout << "static void func调用" << endl;
      	}
      	static int m_A;
      	int m_B;
      	//静态成员函数也是有访问权限的
      private:
      	static void func2()
      	{
      		cout << "static void func2调用" << endl;
      	}
      };
      int Person::m_A = 0;
      void test01()
      {
      	//1.通过对象访问
      	Person p;
      	p.func();
      	//2.通过类名访问
      	Person::func();
      
      	//Person::func2();	//类外不能访问私有静态成员函数
      }
      int main()
      {
      	test01();
      
      	system("pause");
      	return 0;
      }
      ```

### 3.C++对象模型和this指针

#### （1）成员变量和成员函数分开存储（？？）

- 在C++中，类内的成员变量和成员函数分开存储

- 只有非静态成员变量才属于类的对象上

- 示例：

  - ```c++
    #include<iostream>
    #include<string>
    using namespace std;
    
    //成员变量 和 成员函数 分开存储
    class Person
    {
    public:
    	int m_A;	//非静态成员变量，属于类的对象
    	static int m_B;	//静态成员变量，不属于类的对象
    	void func()	{} //非静态成员函数，不属于类的对象
    	static void func2() {}	//静态成员函数，不属于类的对象
    };
    int Person::m_B = 10;
    
    void test01()
    {
    	Person p;
    
    	cout << sizeof(p) << endl;
    	//空对象占用内存空间为：1字节	//因为C++编译器会给每个空对象也分配一个字节空间，为了区分空对象才占内存的，每个空对象也应该有一个独一无二的内存地址
    }
    
    int main()
    {
    	test01();
    
    	system("pause");
    	return 0;
    }
    ```


#### （2）this指针概念

- 每一个非静态变量函数只会诞生一份函数实例，也就是说多个同类型的对象会共用一块代码，那么：这一块代码是如何区分那个对象调用自己呢？
  - C++通过特殊的对象指针，this指针，解决上述问题，**this指针指向被调用的成员函数所属的对象**
  
- this指针是隐含在每一个非静态成员函数内的一种指针

- this指针不需要定义，直接使用即可

- this指针的用途：
  - （解决名称冲突）当形参和成员变量同名时，可用this指针区分
  - （返回对象本身）在类的非静态成员函数中返回对象本身，可使用`return *this`
  
- 示例：

  - ```c++
    #include<iostream>
    #include<string>
    using namespace std;
    
    class Person
    {
    public:
    	Person(int age)	//有参构造
    	{
    		this->age = age;	//使用this指针，指向调用的成员函数所属的对象
    
    	}
    	Person& PersonAddAge(Person &p)
    	{
    		this->age += p.age;
    
    		return *this;	//this是指向p2的指针，而*this指向的就是p2这个对象本体
    	}
    
    	int age;
    };
    
    void test01()
    {
    	Person p1(10);
    	cout << "p1的年龄为：" << p1.age << endl;
    	Person p2(10);
    	p2.PersonAddAge(p1);	//此时为20
    	cout << "p2的年龄为：" << p2.age << endl;
    	//p2.PersonAddAge(p1).PersonAddAge(p1);
    	//cout << "p2的年龄为：" << p2.age << endl;
        p2.PersonAddAge(p2).PersonAddAge(p2);	//是80，而不是60
    	cout << "p2的年龄为：" << p2.age << endl;
    }
    
    int main()
    {
    	test01();
    
    	system("pause");
    	return 0;
    }
    ```


#### （3）空指针访问成员函数

- C++中空指针也是可以直接调用成员函数的，但是要注意有没有用到this指针

- 如果用到this指针，需要加以判断保证代码的健壮性

- 示例：

  - ```c++
    #include<iostream>
    #include<string>
    using namespace std;
    
    class Person
    {
    public:
    	void showClassName()
    	{
    		cout << "this is Person class" << endl;
    	}
    	void showPersonAge()
    	{
    		//出错原因是因为传入的指针为空
    		if (this == NULL)	//判断this指针是否为空
    			return;		//提高代码的健壮性
    		cout << "age = " << this->m_Age << endl;
    	}
    	int m_Age;
    };
    
    void test01()
    {
    	Person* p = NULL;
    	p->showClassName();
    	p->showPersonAge();
    }
    
    int main()
    {
    	test01();
    
    	system("pause");
    	return 0;
    }
    ```


#### （4）const修饰成员函数

- 常函数：
  - 成员函数后加const，我们称这个函数为常函数
  - 常函数内不可以修改成员属性
  - 成员属性声明加关键字`mutable`后，在常函数中依然可以修改
  
- 常对象：
  - 声明对象前加const，称该对象为常对象
  - 常对象只能调用常函数
  
- 示例：

  - ```c++
    #include<iostream>
    #include<string>
    using namespace std;
    
    class Person
    {
    public:
    	void showPerson() const
    	{
    		//this->m_A = 100;	//此时报错：表达式必须是可修改的左值
    		//this指针的本质是指针常量，指针的指向是不可以修改的
    		//this = NULL;	//报错
    		this->m_B = 100;
    	}
    	void func()	{}
    	int m_A;
    	mutable int m_B;	//特殊变量，即使在常函数中，也可以修改这个值，加关键字mutable
    };
    
    void test01()
    {
    	Person p;
    	p.showPerson();
    }
    
    void test02()
    {
    	const Person p2;//在对象前加const，变为常对象
    	//p2.m_A = 100;	//不可修改
    	p2.m_B = 100;	//加了mutable，在常对象下也可以修改
    	//p2.func();	//常对象中不可以调用普通函数，只能调用常函数
    }
    
    int main()
    {
    	test01();
    
    	system("pause");
    	return 0;
    }
    ```


### 4.友元

- 引言：
  - 生活中你的家有客厅（Public），有卧室（Private），客厅所有来的客人都可以进去，但卧室只允许你的好朋友进去；在程序中，有些私有属性也想让类外的一些特殊函数或者类访问，就需要用到友元的技术
- 友元的目的：就是让一个函数或类访问另一个类中的私有成员
- 友元的关键字：`friend`
- 友元的三种实现：
  - 全局函数作友元
  - 类作友元
  - 成员函数作友元

#### （1）全局函数作友元

- 示例：

  - ```c++
    #include<iostream>
    #include<string>
    using namespace std;
    
    class Building
    {
    	friend void goodGay(Building &building);	//友元：声明告诉编译器goodGay全局函数是Building的好朋友，可以访问Building中的私有成员
    public:
    	Building()
    	{
    		m_SittingRoom = "客厅";
    		m_BedRoom = "卧室";
    	}
    
    	string m_SittingRoom;	//客厅
    private:
    	string m_BedRoom;	//卧室
    };
    
    //全局函数
    void goodGay(Building &building)
    {
    	cout << "好基友的全局函数访问：" << building.m_SittingRoom << endl;
    	cout << "好基友的全局函数访问：" << building.m_BedRoom << endl;//未声明友元时不可访问，声明友元后可以访问
    }
    
    void test01()
    {
    	Building building;
    	goodGay(building);
    }
    
    int main()
    {
    	test01();
    
    	system("pause");
    	return 0;
    }
    ```

#### （2）类作友元

- 示例：

  - ```c++
    #include<iostream>
    #include<string>
    using namespace std;
    
    class Building
    {
    	friend class GoodGay;	//类作友元
    public:
    	Building();	//Building的默认构造函数
    	string m_SittingRoom;	//客厅
    private:
    	string m_BedRoom;	//卧室
    };
    
    //类外写成员函数
    Building::Building()
    {
    	m_SittingRoom = "客厅";
    	m_BedRoom = "卧室";
    	cout << "Building的默认构造函数" << endl;
    }
    
    class GoodGay
    {
    public:
    	GoodGay();	//GoodGay的默认构造函数
    	void visit();	//参观函数，用于访问Building中的属性
    	Building* building;
    };
    
    GoodGay::GoodGay()
    {
    	building = new Building;	//堆区创建,利用new创建的数据，会返回该数据对应的类型的指针	//这里会创建一个building的对象
    	cout << "GoodGay的默认构造函数" << endl;
    }
    
    void GoodGay::visit()
    {
    	cout << "GoodGay类正在访问：" << building->m_SittingRoom << endl;
    	cout << "GoodGay类正在访问：" << building->m_BedRoom << endl;	//未声明友元时不可访问，声明友元后可以访问
    }
    
    
    void test01()
    {
    	GoodGay gg;
    	gg.visit();
    }
    
    int main()
    {
    	test01();
    
    	system("pause");
    	return 0;
    }
    ```

#### （3）成员函数作友元

- 示例：

  - ```c++
    #include<iostream>
    #include<string>
    using namespace std;
    
    class Building;	//类的声明
    
    class GoodGay
    {
    public:
    	GoodGay();
    	void visit();	//让visit可以访问Build中的私有成员
    	void visit2();	//visit2不可以访问Build中的私有成员
    	Building* building;
    };
    
    class Building
    {
    	friend void GoodGay::visit();	//成员函数作友元
    public:
    	Building();
    	string m_SittingRoom;	//客厅
    private:
    	string m_BedRoom;	//卧室
    };
    
    //类外写成员函数
    Building::Building()
    {
    	m_SittingRoom = "客厅";
    	m_BedRoom = "卧室";
    }
    GoodGay::GoodGay()
    {
    	building = new Building;	//堆区创建,利用new创建的数据，会返回该数据对应的类型的指针
    }
    void GoodGay::visit()
    {
    	cout << "GoodGay类正在访问：" << building->m_SittingRoom << endl;
    	cout << "GoodGay类正在访问：" << building->m_BedRoom<< endl;	//未声明友元时不可访问，声明友元后可以访问
    }
    void GoodGay::visit2()
    {
    	//cout << "GoodGay类正在访问：" << building->m_SittingRoom << endl;
    	//cout << "GoodGay类正在访问：" << building->m_BedRoom << endl;	
    }
    
    void test01()
    {
    	GoodGay gg;
    	gg.visit();
    	//gg.visit2();
    }
    
    int main()
    {
    	test01();
    
    	system("pause");
    	return 0;
    }
    ```

### 5.运算符重载

- 运算符重载概念：对已有的运算符重新进行定义，赋予其另一种功能，以适应不同的数据类型

#### （1）加号运算符重载

- 作用：实现两个自定义数据类型相加的运算

- 加号运算符重载：

  - 成员函数重载
  - 全局函数重载

- 注意：运算符重载也可以发生函数重载

- 示例：

  - ```c++
    #include<iostream>
    #include<string>
    using namespace std;
    
    //加号运算符重载
    class Person
    {
    public:
    	//1.成员函数重载+号
    	/*Person operator+(Person &p)
    	{
    		Person temp;
    		temp.m_A = this->m_A + p.m_A;
    		temp.m_B = this->m_B + p.m_B;
    		return temp;
    	}*/
    	int m_A;
    	int m_B;
    
    };
    
    //2.全局函数重载+号
    Person operator+(Person &p1, Person &p2)
    {
    	Person temp;
    	temp.m_A = p1.m_A + p2.m_A;
    	temp.m_B = p1.m_B + p2.m_B;
    	return temp;
    }
    //运算符重载也可以发生函数重载
    Person operator+(Person &p1, int num)
    {
    	Person temp;
    	temp.m_A = p1.m_A + num;
    	temp.m_B = p1.m_B + num;
    	return temp;
    }
    
    void test01()
    {
    	Person p1;
    	p1.m_A = 10;
    	p1.m_B = 10;
    	Person p2;
    	p2.m_A = 10;
    	p2.m_B = 10;
    
    	Person p3 = p1 + p2;	//未重载时报错：没有与操作数匹配的+运算符
    	//Person p3 = p1.operator+(p2);	//成员函数本质调用
    	//Person p3 = operator+(p1 , p2);	//全局函数本质调用
    	cout << "p3.m_A = " << p3.m_A << endl;
    	cout << "p3.m_B = " << p3.m_B << endl;
    	Person p4 = p1 + 100;
    	cout << "p4.m_A = " << p4.m_A << endl;
    	cout << "p4.m_B = " << p4.m_B << endl;
    }
    
    
    
    int main()
    
    {
    	test01();
    
    	system("pause");
    	return 0;
    }
    ```

- 总结：

  - 对于内置的数据类型的表达式的运算符是不可能改变的
  - 不要滥用运算符重载
  
- 重载`+=`例题：

  - ```c++
    #include<iostream>
    #include<string>
    using namespace std;
    
    class Point
    {
    private:
    	int x, y;
    public:
    	Point()
    	{
    		x = 0;
    		y = 0;
    	}
    	Point(int x, int y)
    	{
    		this->x = x;
    		this->y = y;
    	}
    	Point& operator+=(const Point &p)
    	{
    		this->x += p.x;
    		this->y += p.y;
    		return *this;
    	}
    	void resetX(int x)
    	{
    		this->x = x;
    	}
    	void resetY(int y)
    	{
    		this->y = y;
    	}
    	int getX()
    	{
    		return this->x;
    	}
    	int getY()
    	{
    		return this->y;
    	}
    
    };
    
    int main()
    {
    	Point p0;
    	cout << p0.getX() << " " << p0.getY() << endl;
    	
    	Point p(2, 3);
    	cout << p.getX() << " " << p.getY() << endl;
    
    	Point p2(5, 5);
    	cout << p2.getX() << " " << p2.getY() << endl;
    
    	p += p2;
    	cout << p.getX() << " " << p.getY() << endl;
    
    	p.resetX(10);
    	p.resetY(10);
    	cout << p.getX() << " " << p.getY() << endl;
    
    	system("pause");
    	return 0;
    }
    ```



#### （2）左移运算符重载

- 作用：可以输出自定义数据类型

- 示例：

  - ```c++
    #include<iostream>
    #include<string>
    using namespace std;
    
    //左移运算符重载
    class Person
    {
    	friend ostream &operator<<(ostream &cout, Person p);
    public:
    	Person(int a, int b)	//有参构造
    	{
    		m_A = a;
    		m_B = b;
    	}
    
    	//1.若成员函数重载 左移运算符	p.operator<<(cout)	简化版本：p << cout
    	//因此通常不使用成员函数重载左移运算符，因为无法实现cout << p
    
    	//成员属性建议设置为私有，全局函数访问时使用友元
    private:
    	
    	int m_A;	//私有成员类外无法访问，但可以用有参构造赋初值
    	int m_B;
    };
    
    //2.全局函数重载 左移运算符（只能使用全局函数）
    //本质：operator << (cout , p)		简化为：cout << p
    //cout 是ostream类型的数据，且使用引用传递
    ostream &operator<<(ostream &cout, Person p)
    {
    	cout << "m_A = " << p.m_A << " m_B = " << p.m_B << endl;
    	return cout;	//链式编程思想
    }
    
    void test01()
    {
    	Person p(10, 20);
    	cout << p << endl;	//左移运算符未重载时报错
    	//本质：operator << (cout , p)		简化为：cout << p
    }
    
    int main()
    {
    	test01();
    
    	system("pause");
    	return 0;
    }
    ```

- 总结：重载左移运算符配合友元可以实现输出自定义数据类型

#### （3）递增运算符重载

- 作用：通过重载递增运算符，实现自己的整形数据

- 示例：

  - ```c++
    #include<iostream>
    #include<string>
    using namespace std;
    
    class MyInteger
    {
    	friend ostream& operator<<(ostream& cout, MyInteger myint);
    public:
    	MyInteger()
    	{
    		m_Num = 0;
    	}
    
    	//重载前置++运算符，返回引用是为了一直对同一个对象操作
    	MyInteger& operator++()
    	{
    		m_Num++;
    		//将自身做一个返回
    		return *this;
    	}
    
    	//重载后置++运算符
    	MyInteger operator++(int)	//(int)占位参数，可以用于区分前置和后置递增
    	{
    		//先记录当时结果
    		MyInteger temp = *this;
    		//后递增
    		m_Num++;
    		//最后将记录结果返回
    		return temp;
    	}
    
    private:
    	int m_Num;
    
    };
    
    ostream& operator<<(ostream& cout, MyInteger myint)
    {
    	cout << myint.m_Num;
    	return cout;
    }
    
    void test01()
    {
    	MyInteger myint;
    	cout << ++(++myint) << endl;
    	cout << myint << endl;	//证明操作的是同一个对象
    }
    
    void test02()
    {
    	MyInteger myint;
    	cout << (myint++)++ << endl;
    	cout << myint << endl;	//后置递增无法连续操作
    }
    
    int main()
    {
    	test01();
    	test02();
    
    	system("pause");
    	return 0;
    }
    ```
  
- 总结：

  - 前置递增返回引用（可以连续递增），后置递增返回值（不可以连续递增）



#### （4）赋值运算符重载

- C++编译器至少给一个类添加四个函数：
  1. 默认构造函数（无参，函数体为空）
  2. 默认析构函数（无参，函数体为空）
  3. 默认拷贝构造函数，对属性进行拷贝
  4. 赋值运算符operator=，对属性进行值拷贝
- 如果类中有属性指向堆区，做赋值操作时也会出现深浅拷贝问题

#### （5）关系运算符重载

- 作用：重载关系运算符，可以让两个自定义数据类型对象进行对比操作

#### （6）函数调用运算符重载

- 函数调用运算符`()`也可以重载
- 由于重载后使用的方法非常像函数调用，因此称为仿函数
- 仿函数没有固定写法，非常灵活

#### （7）重载例题：

##### 例题1：

- 题目：

  - ```c++
    Define and implement a class "MyString" according to the main() and the output in comments.
    int main()
    {
    	MySring s1("012345679"), s2(5), s3;
    	s1.display();	//Output: [012346789]
    	s2.dispaly();	//Output(5 spaces between []): [     ]
    	s3.display();	//Output(no spaces between []): []
    	s3 = s1;
    	s1.display();	//Output: [012346789]
    	s3.display();	//Output: [012346789]
    	s2 = s1 + 3;	
    	s1.display();	//Output: [012346789]
    	s2.dispaly();	//Output: [3456789]
    	s3 = ++++s2;
    	s2.dispaly();	//Output: [56789]
    	s3.dispaly();	//Output: [56789]
    
    
    	return 0;
    }
    ```

- 解答：

  - ```c++
    #include <iostream>
    #include <cstring>
    
    class MyString {
    private:
        char* str;
    
    public:
        // 默认构造函数和带参数的构造函数
        MyString() : str(nullptr) {}
    
        MyString(const char* s) {
            str = new char[strlen(s) + 1];
            strcpy(str, s);
        }
    
        MyString(int n) {
            str = new char[n + 1];
            memset(str, ' ', n);
            str[n] = '\0';
        }
    
        // 拷贝构造函数
        MyString(const MyString& other) {
            str = new char[strlen(other.str) + 1];
            strcpy(str, other.str);
        }
    
        // 析构函数
        ~MyString() {
            delete[] str;
        }
    
        // 赋值运算符重载
        MyString& operator=(const MyString& other) {
            if (this != &other) {
                delete[] str;
                str = new char[strlen(other.str) + 1];
                strcpy(str, other.str);
            }
            return *this;
        }
    
        // + 运算符重载
        MyString operator+(int n) const {
            MyString result(*this);
            if (n >= 0 && n < strlen(str)) {
                result.str += n;
            }
            return result;
        }
    
        // ++ 运算符后缀重载
        MyString operator++(int) {
            MyString temp(*this);
            ++(*this);
            return temp;
        }
    
        // ++ 运算符前缀重载
        MyString& operator++() {
            ++str;
            return *this;
        }
    
        // 显示方法
        void display() const {
            std::cout << "[" << str << "]" << std::endl;
        }
    };
    
    int main() {
        MyString s1("012345679"), s2(5), s3;
        s1.display();   // 输出: [012345679]
        s2.display();   // 输出(5个空格): [     ]
        s3.display();   // 输出(没有空格): []
        s3 = s1;
        s1.display();   // 输出: [012345679]
        s3.display();   // 输出: [012345679]
        s2 = s1 + 3;
        s1.display();   // 输出: [012345679]
        s2.display();   // 输出: [345679]
        s3 = ++++s2;
        s2.display();   // 输出: [5679]
        s3.display();   // 输出: [5679]
    
        return 0;
    }
    
    ```

- 关键：

  - `strcpy()`函数

  - 加号运算符重载

  - 递增运算符重载

  - 赋值运算符重载

  - 


### 6.继承

- 继承是面向对象三大特性之一，定义类时，下一级的成员除了拥有上一级的共性，还有自己的特性，这个时候我们就可以考虑继承的技术，**减少重复代码**

#### （1）继承的基本用法

- 示例：

  - ```c++
    //继承
    class BasePage	//公共页面
    {
    public:
    	void header()
    	{
    		cout << "首页" << endl;
    	}
    };
    
    class Java :public BasePage	//Java界面
    {
    public:
    	void content()
    	{
    		cout << "Java" << endl;
    	}
    };
    
    class CPP :public BasePage	//C++界面
    {
    public:
    	void content()
    	{
    		cout << "CPP" << endl;
    	}
    };
    
    void test01()
    {
    	//Java页面
    	Java ja;
    	ja.header();
    	ja.content();
    	//C++页面
    	CPP cp;
    	cp.header();
    	cp.content();
    }
    ```

- 总结：

  - 继承的好处：可以减少重复的代码
  - 派生类中的成员，包含两大部分：
    - 一类是从基类继承过来的，一类是自己增加的成员
    - 从基类继承过来的表现其共性，新增的成员体现其个性

#### （2）继承方式

- 继承的语法：`class 子类 : 继承方式 父类`

  - 子类：也称 派生类
  - 父类：也称 基类

- 继承方式一共有三种：

  - 公共继承
  - 保护继承
  - 私有继承

- 示例：

  - ```c++
    class Base1
    {
    public:
    	int m_A;
    protected:
    	int m_B;
    private:
    	int m_C;
    };
    
    class Son1 :public Base1
    {
    public:
    	void func()
    	{
    		m_A = 10;	//父类中的公共权限成员，到子类中依然是保护权限
    		m_B = 10;	//父类中的保护权限成员，到子类中依然是保护权限
    		//m_C = 10;	//父类中的私有权限成员，子类访问不到
    	}
    };
    
    class Son2 :protected Base1
    {
    public:
    	void func()
    	{
    		m_A = 10;	//父类中的公共权限成员，到子类中变为保护权限
    		m_B = 10;	//父类中的保护权限成员，到子类中依然是保护权限
    		//m_C = 10;	//父类中的私有权限成员，子类访问不到
    	}
    };
    
    class Son3 :private Base1
    {
    public:
    	void func()
    	{
    		m_A = 10;	//父类中的公共权限成员，到子类中变为 私有成员
    		m_B = 10;	//父类中的保护权限成员，到子类中变为 私有成员
    		//m_C = 10;	//父类中的私有权限成员，子类访问不到
    	}
    };
    
    class Grandson3 :public Son3
    {
    public:
    	void func()
    	{
    		//m_A = 10;	
    		//m_B = 10;	
    		//m_C = 10;	
    		//到了Son3中，三个成员已经全部变为私有，全部不能访问
    	}
    };
    
    void test01()
    {
    	Son1 s1;
    	s1.m_A = 100;
    	//s1.m_B = 100;	//保护权限，类外访问不到
    }
    
    void test02()
    {
    	Son2 s2;
    	//s2.m_A;	//在Son2中 m_A变为了保护权限，类外访问不到
    }
    
    void test03()
    {
    	Son3 s3;
    	//s3.m_A;	//在Son2中 m_A变为了私有成员，类外访问不到
    }
    ```


#### （3）继承中的对象模型

- 问题：从父类继承过来的成员，哪些属于子类对象？

- 示例：

  - ```c++
    #include<iostream>
    #include<string>
    using namespace std;
    
    class Base
    {
    public:
    	int m_A;
    protected:
    	int m_B;
    private:
    	int m_C;
    };
    
    class Son :public Base
    {
    public:
    	int m_D;
    };
    
    void test01()
    {
    	cout << "Son所占内存空间：" << sizeof(Son) << endl;	//16，私有成员也会继承，只是不能访问
    }
    
    
    int main()
    {
    	test01();
    
    	system("pause");
    	return 0;
    }
    ```
  
- 利用开发人员命令提示工具查看对象模型：

  - Vs2013 tools，找开发人员命令提示工具
  - 右击项目中的cpp文件，查看具体路径
  - 输入所在盘，跳转盘符：`E:`
  - 查看命名：cl /d1 reportSingleClassLayout类名 "//键入Tab"所属文件名

#### （4）继承中构造和析构顺序

- 子类继承父类后，当创建子类对象时，也会调用父类的构造函数

- 问题：父类和子类的构造和析构顺序是谁先谁后？

  - 构造：先构造父类，再构造子类
  - 析构：先析构子类，再析构父类

- 注意：

  - 如果子类没有显示调用父类含参数的构造函数，那么在子类实例化过程中
    - 顺序： 父类默认构造函数-->子类被调用的构造函数

  - 如果子类显示调用了父类的含参构造函数，那么在子类实例化过程中
    - 顺序： 父类有参构造函数-->子类被调用的构造函数

- 示例：

  - ```c++
    #include<iostream>
    #include<string>
    using namespace std;
    
    class Base
    {
    public:
    	Base()
    	{
    		cout << "Base的默认构造函数" << endl;
    	}
    	Base(int a)
    	{
    		cout << "Base的有参构造函数" << endl;
    	}
    	~Base()
    	{
    		cout << "Base的析构函数" << endl;
    	}
    };
    
    class Son :public Base
    {
    public:
    	Son()
    	{
    		cout << "Son的默认构造函数" << endl;
    	}
    	Son(int a) :Base(a)	//这属于初始化列表
    	{
    		cout << "Son的有参构造函数" << endl;
    	}
    	~Son()
    	{
    		cout << "Son的析构函数" << endl;
    	}
    };
    
    void test01()
    {
    	//Base b;
    
    	//Son s;
    
    	Son s2(10);
    }
    
    int main()
    {
    	test01();
    
    	system("pause");
    	return 0;
    }
    ```


#### （5）继承中同名成员处理方法

- 问题：当子类与父类出现同名成员时，如何通过子类对象，访问到子类和父类中同名的数据呢？
  - 访问子类同名成员，直接访问即可
  - 访问父类同名成员，需要加作用域
  
- 示例：

  - ```c++
    #include<iostream>
    #include<string>
    using namespace std;
    
    class Base
    {
    public:
    	Base()
    	{
    		m_A = 100;
    	}
    	void func()
    	{
    		cout << "Base的func函数调用" << endl;
    	}
    	void func(int a)
    	{
    		cout << "Base的func(int a)函数调用" << endl;
    	}
    	int m_A;
    };
    
    class Son :public Base
    {
    public:
    	Son()
    	{
    		m_A = 200;
    	}
    	void func()
    	{
    		cout << "Son的func函数调用" << endl;
    	}
    	int m_A;
    };
    
    void test01()
    {
    	Son s;
    	cout << s.m_A << endl;	//直接访问，访问的是子类同名成员
    	cout << s.Base::m_A << endl;	//访问父类同名成员，需要加作用域
    	s.func();	//子类中无与父类同名的函数时，默认直接调用父类的成员函数；子类有时，默认调用子类的同名成员函数
    	s.Base::func();	//访问父类同名成员函数，需要加作用域
    	//s.func(100);	//会报错：因为如果子类出现和父类同名的成员函数，子类的同名成员会隐藏掉父类中所有同名成员函数
    	s.Base::func(100);
    }
    
    int main()
    {
    	test01();
    
    	system("pause");
    	return 0;
    }
    ```

- 总结：

  - 子类出现和父类同名的成员函数，子类的同名成员会隐藏掉父类中所有同名成员函数，加作用域可以访问父类同名函数


#### （6）继承同名静态成员处理方式

- 问题：继承中同名的静态成员在子类对象上如何访问？
  - 静态成员和非静态成员出现同名，处理方式一致
    - 访问子类同名成员，直接访问即可
    - 访问父类同名成员，需要加作用域
  
- 示例：

  - ```c++
    #include<iostream>
    #include<string>
    using namespace std;
    
    class Base
    {
    public:
    	static void func()
    	{
    		cout << "Base的func" << endl;
    	}
    	static void func(int a)
    	{
    		cout << "Base的func(int a)" << endl;
    	}
    	static int m_A;
    };
    int Base::m_A = 100;
    
    class Son :public Base
    {
    public:
    	static void func()
    	{
    		cout << "Son的func" << endl;
    	}
    	static int m_A;
    };
    int Son::m_A = 200;
    
    //同名静态成员属性
    void test01()
    {
    	//1.通过对象访问
    	Son s;
    	cout << s.m_A << endl;
    	cout << s.Base::m_A << endl;
    	//2.通过类名访问
    	cout << Son ::m_A << endl;
    	cout << Base::m_A << endl;	//通过父类访问父类中的m_A
    	cout << Son::Base::m_A << endl;	//通过子类访问父类中的m_A	第一个::表示通过类名访问，第二个::表示访问父类的作用域
    }
    
    //同名静态成员函数
    void test02()
    {
    	//1.通过对象访问
    	Son s;
    	s.func();	//子类没有时，默认正常调用父类的func 子类有时，调用子类的func
    	s.Base::func();
    	//2.通过类名访问
    	Son::func();
    	Son::Base::func();
    	//Son::func(100);	//报错
    	Son::Base::func(100);
    }
    
    int main()
    {
    	test01();
    	test02();
    
    	system("pause");
    	return 0;
    }
    ```

- 总结：同名静态成员处理方法和非静态处理方式一样，只不过有两种访问方式（通过对象和通过类名）

#### （7）多继承语法

- C++允许一个类继承多个类

- 语法：`class 子类 : 继承方式 父类1 , 继承方式 父类2...`

- 多继承可能会引发父类中有同名成员出现，需要加作用域区分

- C++实际开发中不建议用多继承

- 示例：

  - ```c++
    #include<iostream>
    #include<string>
    using namespace std;
    
    class Base1
    {
    public:
    	Base1()
    	{
    		m_A = 100;
    	}
    	int m_A;
    };
    
    class Base2
    {
    public:
    	Base2()
    	{
    		
    		m_A = 200;
    		m_B = 200;
    	}
    	int m_A;
    	int m_B;
    };
    
    class Son :public Base1 , public Base2
    {
    public:
    	Son()
    	{
    		m_C = 300;
    	}
    	int m_C;
    };
    
    void test01()
    {
    	Son s;
    	cout << "sizeof(Son) = " << sizeof(Son) << endl;
    	//cout << s.m_A << endl;	//报错，父类中出现了同名成员。需要加作用域区分
    	cout << "Base1的m_A:" << s.Base1::m_A << endl;
    	cout << "Base2的m_A:" << s.Base2::m_A << endl;
    }
    
    int main()
    {
    	test01();
    
    	system("pause");
    	return 0;
    }
    ```


#### （8）菱形继承

- 菱形继承概念：
  - 两个派生类继承同一个基类
  - 又有某个类同时继承两个派生类
  - 这种继承被称为菱形继承，或钻石继承
  
- 菱形继承问题：

  - 子a继承了父类的数据，子b也继承了父类的数据，当孙使用时，就会产生二义性
  - 孙继承自父类的数据继承了两份，而实际上这份数据我们只需要一份即可

- 示例：

  - ```c++
    #include<iostream>
    #include<string>
    using namespace std;
    
    class Animal	//动物类
    {
    public:
    	int m_Age;
    };
    //利用虚继承 解决菱形问题继承的问题
    //继承之前，加上关键字virtual变为虚继承（？？？）
    //Animal类称为 虚基类
    
    class Sheep :virtual public Animal	//羊
    {
    public:	
    };
    
    class LuoTuo :virtual public Animal	//骆驼
    {
    public:
    };
    
    class YangTuo :public Sheep, public LuoTuo	//羊驼
    {
    public:
    };
    
    void test01()
    {
    	YangTuo yt;
    	//yt.m_Age = 20;	//报错：不明确
    	//当菱形继承时，两个父类具有相同数据，需要加作用域区分
    	yt.Sheep::m_Age = 10;
    	yt.LuoTuo::m_Age = 11;
    	cout << "yt.Sheep::m_Age:" << yt.Sheep::m_Age << endl;
    	cout << "yt.LuoTuo::m_Age:" << yt.LuoTuo::m_Age << endl;
    	cout << "yt.m_Age:" << yt.m_Age << endl;
    }
    
    int main()
    {
    	test01();
    
    	system("pause");
    	return 0;
    }
    ```

- 总结：

  - 菱形继承带来的主要问题是子类继承俩份相同的数据，导致资源浪费以及毫无意义
  - 利用虚继承可以解决菱形继承问题


### 7.多态

#### （1）多态的基本概念

- 多态时C++面向对象三大特性之一

- 多态分为两大类：
  - 静态多态：函数重载和运算符重载属于静态多态，复用函数名
  - 动态多态：派生类和虚函数实现运行时多态
    - 动态多态满足条件：
       	1. 有继承关系
        	2. 子类要重写父类中的虚函数
            - 重写：函数返回值类型 函数名 形参列表 完全相同
    - 动态多态的使用：父类的指针或引用指向子类对象
  
- 静态多态和动态多态区别：
  - 静态多态的函数地址早绑定 - 编译阶段确定函数地址
  - 动态多态的函数地址晚绑定 - 运行阶段确定函数地址
  
- 示例：

  - ```c++
    #include<iostream>
    #include<string>
    using namespace std;
    
    class Animal	//动物类
    {
    public:
    
    	virtual void speak()	//虚函数
    	{
    		cout << "动物在说话" << endl;
    	}
    };
    
    class Cat :public Animal
    {
    public:
    	void speak() override
    	{
    		cout << "小猫在说话" << endl;
    	}
    };
    
    class Dog :public Animal
    {
    public:
    	void speak() override
    	{
    		cout << "小狗在说话" << endl;
    	}
    };
    
    //地址早绑定	在编译阶段确定函数地址
    //如果想执行让猫说话，那么这个函数地址就不能提前绑定，需要在运行阶段进行绑定，地址晚绑定
    //动态多态满足条件：1.有继承关系	2.子类要重写父类中的虚函数
    //重写：函数返回值类型 函数名 形参列表完全相同
    void dospeak(Animal &animal)	//Animal &animal = cat;
    {
    	animal.speak();
    }
    
    void test01()
    {
    	Cat cat;
    	dospeak(cat);
    	Dog dog;
    	dospeak(dog);
    }
    
    int main()
    {
    	test01();
    
    	system("pause");
    	return 0;
    }
    ```

- 派生类可以覆盖基类中的虚函数，方法是使用`override`关键字，使用`override`关键字有助于编译器检查，确保派生类中的函数确实是基类中虚函数的覆盖。

- 多态的原理剖析：

  - vfpter  ---  虚函数（表）指针
    - v  ---  virtual
    - f  ---  function
    - ptr --- pointer

  - vftable ---  虚函数表
  - 当子类重写父类的虚函数，子类中的虚函数表内部会替换成子类的虚函数地址
  - 当父类的指针或引用指向子类对象时，发生多态
  
- 补充：

  - 父类指针指向子类对象，调用非虚函数的同名函数调用的是父类的成员函数，这是因为非虚函数在编译时就确定了调用哪个版本，而不会根据实际对象类型动态绑定。这种行为被称为静态绑定或早期绑定

  - 父类指针指向子类对象，调用虚函数的同名函数（也就是重写的同名函数）调用的是子类的成员函数，也就是多态

  - ```c++
    #include<iostream>
    #include<string>
    using namespace std;
    
    class B
    {
    public:
    	void m()
    	{
    		cout << "B::m" << endl;
    	}
    	virtual void f()
    	{
    		cout << "B::f" << endl;
    	}
    };
    
    class D :public B
    {
    public:
    	void m()
    	{
    		cout << "D::m" << endl;
    	}
    	void f()
    	{
    		cout << "D::f" << endl;
    	}
    };
    
    int main()
    {
    	B *p[2];
    	p[0] = new D;
    	p[1] = new B;
    
    	p[0]->m();
    	p[0]->f();
    
    	p[1]->m();
    	p[1]->f();
    
    	system("pause");
    	return 0;
    }
    ```

  - 



#### （2）多态案例1  -  计算机类

- 案例描述：
  - 分别用普通写法和多态技术，设计实现两个操作数进行运算的计算机类
- 多态的优点：
  - 代码组织结构清晰
  - 可读性强
  - 利于前期和后期的拓展和维护
  
- 文件：[14.多态案例1-计算器类.cpp](https://github.com/zzx051900/CPP/blob/d647ee7f4d9451703b91856c796d73aae74c7ba4/C%2B%2B%E7%A8%8B%E5%BA%8F%E7%BB%83%E4%B9%A0%E4%BB%A3%E7%A0%81/14.%E5%A4%9A%E6%80%81%E6%A1%88%E4%BE%8B1-%E8%AE%A1%E7%AE%97%E5%99%A8%E7%B1%BB.cpp)

- 代码：

  - ```c++
    #include<iostream>
    #include<string>
    using namespace std;
    
    //分别利用普通写法和多态写法实现计算器
    
    //普通写法
    class Calculator
    {
    public:
    	int getResult(string oper)
    	{
    		if (oper == "+")
    		{
    			return m_Num1 + m_Num2;
    		}
    		else if (oper == "-")
    		{
    			return m_Num1 - m_Num2;
    		}
    		else if (oper == "*")
    		{
    			return m_Num1 * m_Num2;
    		}
    		//如果要提供新的功能，还需要修改源码
    		//而在真实的开发中提倡一种原则：开闭原则（对拓展进行开放，对修改进行关闭）
    	}
    	int m_Num1;
    	int m_Num2;
    };
    
    void test01()
    {
    	Calculator c;
    	c.m_Num1 = 10;
    	c.m_Num2 = 20;
    	cout << c.m_Num1 << " + " << c.m_Num2 << " = " << c.getResult("+") << endl;
    	cout << c.m_Num1 << " - " << c.m_Num2 << " = " << c.getResult("-") << endl;
    	cout << c.m_Num1 << " * " << c.m_Num2 << " = " << c.getResult("*") << endl;
    }
    
    //用多态实现计算器
    //多态带来的好处：1.组织结构清晰	2.可读性强	3.对于前期和后期拓展以及维护性高
    
    //实现计算器抽象类
    class AbstractCalculator
    {
    public:
    	virtual int getResult()	//虚函数，在子类进行重写
    	{
    		return 0;
    	}
    	int m_Num1;
    	int m_Num2;
    };
    
    //加法计算器类
    class AddClaculator :public AbstractCalculator
    {
    public:
    	int getResult()
    	{
    		return m_Num1 + m_Num2;;
    	}
    };
    
    //减法计算器类
    class SubClaculator :public AbstractCalculator
    {
    public:
    	int getResult()
    	{
    		return m_Num1 - m_Num2;;
    	}
    };
    
    //乘法计算器类
    class MulClaculator :public AbstractCalculator
    {
    public:
    	int getResult()
    	{
    		return m_Num1 * m_Num2;;
    	}
    };
    
    void test02()
    {
    	//加法运算
    	AbstractCalculator *abc = new AddClaculator;	///父类的指针或引用指向子类对象
    	abc->m_Num1 = 10;
    	abc->m_Num2 = 20;
    	cout << abc->m_Num1 << " + " << abc->m_Num2 << " = " << abc->getResult()  << endl;
    	delete abc;	//堆区开辟的数据要销毁
    	//减法运算
    	abc = new SubClaculator;
    	abc->m_Num1 = 10;
    	abc->m_Num2 = 20;
    	cout << abc->m_Num1 << " - " << abc->m_Num2 << " = " << abc->getResult() << endl;
    	delete abc;	//堆区开辟的数据要销毁
    	//乘法运算
    	abc = new MulClaculator;
    	abc->m_Num1 = 10;
    	abc->m_Num2 = 20;
    	cout << abc->m_Num1 << " * " << abc->m_Num2 << " = " << abc->getResult() << endl;
    	delete abc;	//堆区开辟的数据要销毁
    }
    
    int main()
    {
    	test01();
    	test02();
    
    	system("pause");
    	return 0;
    }
    ```

- 总结：

  - C++开发中提倡利用多态设计程序架构，因为多态优点很多
  - 多态带来的好处：
     	1. 组织结构清晰	
     	2. 可读性强	
     	3. 对于前期和后期拓展以及维护性高


#### （3）纯虚函数和抽象类

- 在多态中，通常父类中虚函数的实现是无意义的，主要都是调用子类重写的内容，因此可以将虚函数改为纯虚函数

- 纯虚函数语法：`virtual 返回值类型 函数名(参数列表) = 0;`

- 当类中有了纯虚函数（只要有一个就可以），这个类称为抽象类

- 抽象类特点：
  - 无法实例化对象
  - 子类必须重写抽象类中的纯虚函数，否则也属于抽象类
  
- 示例：

  - ```c++
    #include<iostream>
    #include<string>
    using namespace std;
    
    class Base
    {
    public:
    	//纯虚函数，只要有一个，这个类就是抽象类
    	virtual void func() = 0;
    };
    
    class Son1 :public Base
    {
    public:
    	virtual void func()
    	{
    		cout << "Son1的func函数调用" << endl;
    	};
    };
    
    class Son2 :public Base
    {
    public:
    	virtual void func()
    	{
    		cout << "Son2的func函数调用" << endl;
    	};
    };
    
    void test01()
    {
    	//抽象类无法实例化对象
    	//Base b;
    	//new Base;
    	//Son s;	//子类必须重写父类中的纯虚函数，否则无法实例化对象
    	Base* base = new Son1;
    	base->func();
    	delete base;
    	base = new Son2;
    	base->func();
    	delete base;
    	//多态的目的就是为了让函数的接口更通用化，通过一个父类指针，指针不同对象时可以调用多种形态的函数
    }
    
    int main()
    {
    	test01();
    
    	system("pause");
    
    	return 0;
    }
    ```


#### （4）多态案例2  -  制作饮品

- 案例描述：
  - 制作饮品的大致流程为：煮水 - 冲泡 - 倒入杯中 - 加入辅料
  - 利用多态技术实现本案例，提供抽象类制作饮品基类，提供子类制作咖啡和茶叶
  
- 文件：[15.多态案例2-制作饮品.cpp](https://github.com/zzx051900/CPP/blob/d647ee7f4d9451703b91856c796d73aae74c7ba4/C%2B%2B%E7%A8%8B%E5%BA%8F%E7%BB%83%E4%B9%A0%E4%BB%A3%E7%A0%81/15.%E5%A4%9A%E6%80%81%E6%A1%88%E4%BE%8B2-%E5%88%B6%E4%BD%9C%E9%A5%AE%E5%93%81.cpp)

- 代码：

  - ```c++
    #include<iostream>
    #include<string>
    using namespace std;
    
    class AbstractDrinking	//抽象类：制作饮品类
    {
    public:
    	virtual void Boil() = 0;0		//煮水
    	virtual void Brew() = 0;		//冲泡
    	virtual void PourInCup() = 0;	//倒入杯中
    	virtual void PutSomething() = 0;//加入辅料
        
    	void makeDrink()	//制作饮品（将所有步骤作一个封装）
    	{
    		Boil();
    		Brew();
    		PourInCup();
    		PutSomething();
    	}
    };
    
    class Coffee :public AbstractDrinking	//咖啡类0
    {
    public:
    	virtual void Boil()
    	{
    		cout << "煮水" << endl;
    	}
    	virtual void Brew()
    	{
    		cout << "冲泡咖啡" << endl;
    	}
    	virtual void PourInCup()
    	{
    		cout << "倒入杯中" << endl;
    	}
    	virtual void PutSomething()
    	{
    		cout << "加入糖和牛奶" << endl;
    	}
    };
    
    class Tea :public AbstractDrinking	//茶类
    {
    public:
    	virtual void Boil()
    	{
    		cout << "煮矿泉水" << endl;
    	}
    	virtual void Brew()
    	{
    		cout << "冲泡茶叶" << endl;
    	}
    	virtual void PourInCup()
    	{
    		cout << "倒入杯中" << endl;
    	}
    	virtual void PutSomething()
    	{
    		cout << "加入枸杞" << endl;
    	}
    };
    
    void doWork(AbstractDrinking* abs)	//传入一个父类的指针 //这一个函数是因为咖啡和茶都要用到，所以单独封装了这一步
    {
    	abs->makeDrink();
    	delete abs;
    	abs = NULL;
    }
    
    void test01()
    {
    	//制作咖啡
    	doWork(new Coffee);
    	cout << "------------" << endl;
    	//制作茶叶
    	doWork(new Tea);
    }
    
    int main()
    {
    	test01();
    
    	system("pause");
    	return 0;
    }
    ```


#### （5）虚析构和纯虚析构

- 多态使用时，如果子类中有属性开辟到堆区，那么在父类指针在释放时无法调用到子类的析构代码
- 解决方法：将父类中的析构函数改为虚析构或纯虚析构
- 虚析构和纯虚析构共性：
  - 可以解决父类指针释放子类对象
  - 都需要有具体的函数实现
- 虚析构和纯虚析构区别：
  - 如果是纯虚析构，该类属于抽象类，无法实例化对象
- 虚析构语法：`virtual ~类名(){}`
- 纯虚析构语法：
  - `virtual ~类名() = 0`
  - `类名::~类名(){}`
  
- 示例：

  - ```c++
    #include<iostream>
    #include<string>
    using namespace std;
    
    class Animal
    {
    public:
    	Animal()
    	{
    		cout << "Animal构造函数调用" << endl;
    	}
    	//virtual ~Animal()	//利用虚析构可以解决：父类指针释放子类对象时不干净的问题
    	//{
    	//	cout << "Animal虚析构函数调用" << endl;
    	//}
    	virtual ~Animal() = 0;	//纯虚析构必须有声明和实现（因为父类中堆区空间必须由父类的析构函数释放）
    	//只要有了纯虚析构，就属于抽象类。无法 实例化对象
    	virtual void speak() = 0;	//纯虚函数,纯虚函数可以只有声明没有实现
    };
    Animal::~Animal()
    {
    	cout << "Animal纯虚析构函数调用" << endl;
    }
    
    
    class Cat : public Animal
    {
    public:
    	Cat(string name)
    	{
    		cout << "Cat构造函数调用" << endl;
    		m_Name = new string(name);	//堆区创建了一块内存，需要手动释放
    	}
    	virtual void speak()
    	{
    		cout << *m_Name << "小猫说话" << endl;
    	}
    	~Cat()
    	{
    		cout << "Cat析构函数调用" << endl;
    		if (m_Name)
    		{
    			delete m_Name;
    			m_Name = NULL;
    		}
    	}
    	string* m_Name;
    };
    
    void test01()
    {
    	Animal* animal = new Cat("Tom");
    	animal->speak();
    	delete animal;
    	//父类指针析构时，不会调用子类中析构函数，导致如果子类有堆区属性，会出现内存泄露
    	//解决办法，将父类析构函数改为虚析构
    }
    
    int main()
    {
    	test01();
    
    	system("pause");
    	return 0;
    }
    ```
  
- 总结：

  - 虚析构或者纯虚析构就是用来解决通过父类指针释放子类对象
  - 如果子类中没有堆区数据，可以不写虚析构或纯虚析构
  - 若未使用虚析构，父类指针析构时，不会调用子类中析构函数，导致如果子类有堆区属性，会出现内存泄露
  - 纯虚析构必须有声明和实现（因为父类中堆区空间必须由父类的析构函数释放）
  - 只要有了纯虚析构，就属于抽象类。无法 实例化对象


#### （6）多态案例3  -  电脑组装

- 案例描述;

  - 电脑主要组成部件为CPU、显卡、内存条
  - 将每个零件封装出抽象基类，并且提供不同的厂商生产不同的零件，例如Intel厂商和Lenovo厂商
  - 创建电脑类提供让电脑工作的函数，并且调用每个零件工作的接口
  - 测试时组装三台不同的电脑进行工作

- 文件：[16.多态案例3-电脑组装.cpp](https://github.com/zzx051900/CPP/blob/d647ee7f4d9451703b91856c796d73aae74c7ba4/C%2B%2B%E7%A8%8B%E5%BA%8F%E7%BB%83%E4%B9%A0%E4%BB%A3%E7%A0%81/16.%E5%A4%9A%E6%80%81%E6%A1%88%E4%BE%8B3-%E7%94%B5%E8%84%91%E7%BB%84%E8%A3%85.cpp)

- 代码：

  - ```c++
    #include<iostream>
    #include<string>
    using namespace std;
    
    //抽象CPU类
    class CPU
    {
    public:
    	//抽象计算函数
    	virtual void calculate() = 0;	//纯虚函数
    };
    
    //抽象显卡类
    class VideoCard
    {
    public:
    	//抽象显示函数
    	virtual void display() = 0;	//纯虚函数
    };
    
    //抽象内存条类
    class Memory
    {
    public:
    	//抽象存储函数
    	virtual void storage() = 0;	//纯虚函数
    };
    
    //电脑类
    class Computer
    {
    public:
    	Computer(CPU* cpu, VideoCard* vc, Memory* mem)	//有参构造
    	{
    		m_cpu = cpu;
    		m_vc = vc;
    		m_mem = mem;
    	}
    	void work()	//零件工作函数，调用具体接口
    	{
    		m_cpu->calculate();
    		m_vc->display();
    		m_mem->storage();
    	}
    	~Computer()
    	{
    		//释放CPU零件
    		if (m_cpu)
    		{
    			delete m_cpu;
    			m_cpu = NULL;
    		}
    		//释放显卡零件
    		if (m_vc)
    		{
    			delete m_vc;
    			m_cpu = NULL;
    		}
    		//释放内存条零件
    		if (m_mem)
    		{
    			delete m_mem;
    			m_mem = NULL;
    		}
    	}
    
    private:
    	CPU* m_cpu;	//CPU的零件指针
    	VideoCard* m_vc;	//显卡零件指针	
    	Memory* m_mem;	//内存条零件指针
    };
    
    //具体厂商：
    	//Intel厂商:
    		//CPU
    class IntelCPU :public CPU
    {
    public:
    	virtual void calculate()
    	{
    		cout << "Intel的CPU开始计算" << endl;
    	}
    };
    		//显卡
    class IntelVideoCard :public VideoCard
    {
    public:
    	virtual void display()
    	{
    		cout << "Intel的显卡开始显示" << endl;
    	}
    };
    		//内存条
    class IntelMemory  :public Memory
    {
    public:
    	virtual void storage()
    	{
    		cout << "Intel的内存条开始存储" << endl;
    	}
    };
    
    	//Lenovo厂商：
    		//CPU
    class LenovoCPU :public CPU
    {
    public:
    	virtual void calculate()
    	{
    		cout << "Lenovo的CPU开始计算" << endl;
    	}
    };
    		//显卡
    class LenovoVideoCard :public VideoCard
    {
    public:
    	virtual void display()
    	{
    		cout << "Lenovo的显卡开始显示" << endl;
    	}
    };
    		//内存条
    class LenovoMemory :public Memory
    {
    public:
    	virtual void storage()
    	{
    		cout << "Lenovo的内存条开始存储" << endl;
    	}
    };
    
    //测试组装不同电脑
    void test01()
    {
    	//第一台电脑零件（用Intel的电脑零件）
    	CPU* intelCPU = new IntelCPU;	//父类指针指向子类对象，多态	//堆区创建
    	VideoCard* intelVideoCard = new IntelVideoCard;
    	Memory* intelMemory = new IntelMemory;
    
    	//创建第一台电脑
    	cout << "第一台电脑开始工作" << endl;
    	Computer* computer1 = new Computer(intelCPU, intelVideoCard, intelMemory);
    	computer1->work();
    	delete computer1;	//此时只释放了电脑类指针在堆区的内存，而零件在堆区的内存还没有释放
    
    	//创建第二台电脑（用Lenovo的电脑零件）
    	cout << "----------------" << endl;
    	cout << "第二台电脑开始工作" << endl;
    	Computer* computer2 = new Computer(new LenovoCPU, new LenovoVideoCard, new LenovoMemory);
    	computer2->work();
    	delete computer2;
    
    	//创建第三台电脑（混合搭配）
    	cout << "----------------" << endl;
    	cout << "第三台电脑开始工作" << endl;
    	Computer* computer3 = new Computer(new IntelCPU, new LenovoVideoCard, new LenovoMemory);
    	computer3->work();
    	delete computer3;
    }
    
    int main()
    {
    	test01();
    
    	system("pause");
    	return 0;
    }
    ```
  
#### （7）多态例题

  ##### 例题1：

  - 题目：
  
    - ```c++
      According to the main function and thw output below,implement a class hierarchy whith fighter as the base class and Warrior is a derived class from fighter.
      int main()
      {
      	fighter* objs[2];
      	objs[0] = new fighter("Harry");
      	Warrior Stallone("Stallone", objs[0]);
      	objs[1] = &Stallone;
      	cout << "Test the class famliy:" << endl;
      	for (int i = 0; i < 2; i++)
      	{
      		objs[i]->outTitle();
      		cout << i + 1 << endl;
      		objs[i]->hello();
      	}
      	cout << "This is the end" << endl;
      	delete objs[0];
      
      	return 0;
      }
      The output:
      Test the class family :
      We are fighters.
      1
      Harry is a fighter.
      We are fighters.
      2
      Stallone is a stronger warrior than Harry.
      This is the end
      ```
  
  - 作答：
  
    - ```c++
      class fighter 
      {
      public:
      	fighter(const string& n)
      	{
      		name = n;
      	}
      
      	virtual void outTitle() const 
      	{
      		cout << "We are fighters." << endl;
      	}
      
      	virtual void hello() const {
      		cout << name << " is a fighter." << endl;
      	}
      
      	virtual ~fighter() {}
      	string name;
      };
      
      class Warrior : public fighter {
      public:
      	Warrior(const string& n, fighter* base) : fighter(base->name)
      	{
      		s_name = n;
      	}
      
      	void outTitle() const override 
      	{
      		cout << "We are fighters." << endl;
      	}
      
      	void hello() const override 
      	{
      		cout << s_name << " is a stronger warrior than " << name << endl;
      	}
      
      	string s_name;
      };
      
      //改为同名成员时，直接调用为子类中的name，父类中的name需要增加作用域
      /*
      class Warrior : public fighter {
      public:
      	Warrior(const string& n, fighter* base) : fighter(base->name)
      	{
      		name = n;
      	}
      	void hello() const override 
      	{
      		cout << name << " is a stronger warrior than " << fighter::name << endl;
      	}
      
      	string name;
      };
      */
      ```
    
  - 注意：

    - **const**：在成员函数声明和定义中使用 `const` 表示该成员函数是一个常量成员函数，即在函数体内不能修改对象的成员变量
    - **override**：在成员函数声明中使用 `override` 关键字表示该函数是一个重写（覆盖）基类中的虚函数。这有助于确保子类中的函数确实是重写了基类中的虚函数
    - 子类即使不重写（覆盖）父类的虚函数，仍然可以调用父类的虚函数。在这种情况下，子类对象的调用将直接调用父类的实现。如果父类中的虚函数被声明为虚函数，则它在派生类中仍然是虚函数。
        - 重写虚函数的主要目的是允许子类提供自己的实现，以替代从父类继承的实现。这样，当通过基类指针或引用调用虚函数时，实际执行的是派生类中的版本，而不是基类中的版本。以下是一些使用虚函数重写的主要原因：
            1. **多态性（Polymorphism）：** 通过重写虚函数，可以实现多态性，即通过基类指针或引用调用虚函数时，可以在运行时确定实际执行的是哪个版本的函数。这是面向对象编程中的一个关键概念，使得程序更加灵活和可扩展
            2. **定制化行为：** 派生类可能需要提供特定于自身的行为，而不仅仅是继承基类的实现。通过重写虚函数，可以在派生类中定制化函数的行为
            3. **确保正确的行为：** 在某些情况下，基类可能提供一个默认的实现，但派生类需要提供更具体或特殊化的实现。通过重写虚函数，可以确保在派生类中使用正确的实现
        - 



## （五）文件操作

- 引言：
  - 程序运行时产生的数据都属于临时数据，程序一旦运行结束都会被释放；
  - 而通过文件，可以将数据持久化；
- C++中对文件操作需要包含头文件`<fstream>`
- 文件类型分为两种：
  1. 文本文件：文件以文本的ASCII码存储在计算机中
  2. 二进制文件：文件以文本的二进制形式存储在计算机中，用户一般不能直接读懂它们
- 操作文件的三大类：
  - `ofstream`：写操作，用于创建对象并写入
  - `ifstream`：读操作，用于从文件读取信息。
  - `fstream`：读写操作，该数据类型通常表示文件流，且同时具有 `ofstream` 和 `ifstream `两种功能，这意味着它可以创建文件，向文件写入信息，从文件读取信息。

### 1.文本文件

#### （1）写文件

- 写文件的步骤：

  1. 包含头文件：`#include<fstream>`
  2. 创建流对象：`ofstream ofs;`
  3. 打开文件：`ofs.open("文件路径",打开方式);`
     - 文件打开方式：
       - `ios::in`：为读文件打开文件
       - `ios::out`：为写文件打开文件
       - `ios::ate`：初始位置，文件尾
       - `ios::app`：追加方式写文件
       - `ios::trunc`：如果文件存在，则先删除，再创建
       - `ios::binary`：二进制方式
     - 注意：文件打开方式可以配合使用，利用`|`操作符
       - 例：用二进制方式写文件：`ios::binary | ios::out`
  4. 写文件：`ofs << "写入的数据";`
     - 流插入运算符 `<< `
  5. 关闭文件：`ofs.close();`

- ```c++
  #include<iostream>
  #include<fstream>//1.包含头文件
  using namespace std;
  //文本文件写文件
  void test01()
  {
  	ofstream ofs;//2.创建流对象
  	ofs.open("test.txt", ios::out);//3.打开方式
  	ofs << "姓名：张三" << endl;//4.写内容
  	ofs.close();//5.关闭文件
  }
  int main()
  {
  	test01();
  	system("pause");
  	return 0;
  }
  ```

- 总结：

  - 文件操作必须包含头文件`<fstream>`
  - 读文件可以利用ofstream，或fstream类
  - 打开文件时需要指定操作文件的路径，以及打开方式
  - 利用`<<`可以向文件中写数据
  - 操作完毕，要关闭文件

#### （2）读文件

- 写文件的步骤：

  1. 包含头文件：`#include<fstream>`
  2. 创建流对象：`ifstream ifs;`
  3. 打开文件：`ifs.open("文件路径",打开方式);`
  4. 读文件：四种方式读取
     - 流提取运算符`>> `
  5. 关闭文件：`ifs.close();`

- ```c++
  #include<iostream>
  #include<fstream>//1.包含头文件
  #include<string>
  using namespace std;
  //文本文件读文件
  void test01()
  {
  	ifstream ifs;//2.创建流对象
  	ifs.open("test.txt", ios::in);//3.打开方式
  	if (!ifs.is_open())	//判断文件是否打开成功;成功为true,失败为false
  	{
  		cout << "文件打开失败" << endl;
  		return;//若文件打开失败，则直接返回
  	}
  	//4.读数据
  	//第一种：
  	/*char buf[1024] = { 0 };
  	while (ifs >> buf)
  	{
  		cout << buf << endl;
  	}*/
  	//第二种：
  	/*char buf[1024] = { 0 };
  	while (ifs.getline(buf, sizeof(buf)))
  	{
  		cout << buf << endl;
  	}*/
  	//第三种：
  	/*string buf;
  	while (getline(ifs, buf))	//要包含头文件<string>
  	{
  		cout << buf << endl;
  	}*/
  	//第四种（不推荐，效率低）：
  	char c;
  	while ((c = ifs.get()) != EOF) //EOF：end of file；意思就是如果没有到文件尾就一直读，读一个字符，输出一个字符
  	{
  		cout << c;
  	}
  	ifs.close();//5.关闭文件
  }
  int main()
  {
  	test01();
  	system("pause");
  	return 0;
  }
  ```

### 2.二进制文件

## （六）命名空间

- 在C++中通过引入命名空间的概念，来解决命名冲突的问题，当在C++中编写大型程序时，很容易出现变量名和函数名冲突的问题。为了解决这个问题，C++引入了命名空间（Namespace）的概念，允许程序员将代码组织成独立的、可重用的模块。命名空间提供了一种将相关的变量、函数和类组织在一起的方式，以避免全局命名冲突。
- 简单来说C++中的命名空间就是定义了一个范围
- 注意：
  - 因为C++是多编译器，接近底层，项目结构设计难度一般的编程语言
  - 命名空间就显得十分重要，一定要熟练掌握
  - 否则在调试程序或阅读源码时将会十分困难

### 1.using namespace std

- 只在main.cpp中加入（只在主文件0中加入using namespace std）
- using namespace std
  - 将"std"中所有内容引入目前的命名空间中
  - 好处：大多数情况下会少写很多东西，使得代码更可读
  - 坏处：有可能导致命名空间被污染（？？？）

### 2.创建命名空间

### 3.Default Global Namespace

### 4.Using的用法

#### （1）引入命名空间中的名称

- 通过 `using namespace`，可以将整个命名空间引入当前的作用域，从而避免使用作用域解析运算符 `::`

  - ```c++
    #include <iostream>
    
    // 引入整个命名空间
    using namespace std;
    
    int main() {
        cout << "Hello, World!" << endl;
        return 0;
    }
    ```

  - 在上面的例子中，`using namespace std;` 允许在 `main` 函数中直接使用 `cout` 和 `endl`，而不需要写成 `std::cout` 和 `std::endl`。

#### （2）引入特定的名称

- 可以使用 `using` 引入命名空间中的特定名称，而不是整个命名空间

  - ```c++
    #include <iostream>
    
    // 引入特定的名称
    using std::cout;
    using std::endl;
    
    int main() {
        cout << "Hello, World!" << endl;
        return 0;
    }
    ```

    - 在这个例子中，只引入了 `std` 命名空间中的 `cout` 和 `endl`

  - ```c++
    namespace MyNamespace {
        int myVariable;
    }
    
    using MyNamespace::myVariable;
    
    int main() {
        myVariable = 42;
        return 0;
    }
    ```

    - 在这个例子中，只引入了一个`int`类型的变量

  - ```c++
    namespace MyNamespace {
        void myFunction() { /* ... */ }
    }
    
    using MyNamespace::myFunction;
    
    int main() {
        myFunction();
        return 0;
    }
    ```

    - 引入一个函数

  - ```c++
    namespace MyNamespace {
        class MyClass { /* ... */ }
    }
    
    using MyNamespace::MyClass;
    
    int main() {
        MyClass obj;
        return 0;
    }
    
    ```

    - 引入一个类

#### （3） 给名称提供别名

- 使用 `using` 还可以为某个名称提供别名，这在特定的上下文中可能很有用

  - ```c++
    #include <iostream>
    
    // 为名称提供别名
    using MyAlias = std::string;
    
    int main() {
        MyAlias myString = "Hello, Alias!";
        std::cout << myString << std::endl;
        return 0;
    }
    ```

  - 在这个例子中，`MyAlias` 是 `std::string` 的别名，可以在程序中使用 `MyAlias` 来代替 `std::string`。

#### （4）在函数内引入

- 可以在函数内部使用 `using`，使其在函数作用域内生效，而不是在整个文件中生效

  - ```c++
    #include <iostream>
    
    void myFunction() 
    {
        using namespace std; // 在函数内引入命名空间
        cout << "Inside function." << endl;
    }
    
    int main() 
    {
        myFunction();
        // cout << "Outside function." << endl; // 这里无法直接使用 cout
        return 0;
    }
    ```

  - 在上述示例中，`using namespace std;` 只在 `myFunction` 函数内部生效，因此在 `main` 函数中不能直接使用 `cout`。

#### 注意事项：

- **避免滥用：** 尽管 `using` 可以使代码更简洁，但滥用它可能导致命名冲突或不明确的代码。在全局范围内使用 `using namespace` 可能引起不必要的问题，因此最好只在局部范围内使用。
- **头文件中的使用：** 通常不建议在头文件中使用 `using namespace`，因为这可能会导致在包含头文件的文件中引入不必要的命名空间。

- 总体来说，`using` 是一种方便的工具，但在使用时需要谨慎，以免引发潜在的问题。

### 5.嵌套命名空间与别名

#### 命名空间的嵌套

- 可以在其他命名空间内定义命名空间，从而创建嵌套的命名空间结构：

  - ```c++
    namespace OuterNamespace 
    {
        namespace InnerNamespace 
        {
            // 命名空间中的代码
        }
    }
    ```

#### 命名空间的别名

- 可以为命名空间定义别名，以简化使用：

  - ```c++
    namespace ns = MyNamespace;
    int result = ns::myFunction(2, 3);
    ```

## （七）异常处理

### 1.什么是异常和异常处理

- 异常就是程序在运行过程中出现的问题
- “异常”问题并不经常出现
- 异常处理技术使我们写可以写程序解决出现的异常问题
- 很多情况下，处理了异常就能使程序像没发生过问题一样继续执行
- 严重的问题也许使程序不能继续执行，使用异常处理技术可以用可控的方式对用户发出警示，然后再终止程序
- 异常处理技术，可以使我们能够编写更健壮、更具容错性的程序，能处理发生的问题使程序继续执行，或者优雅地终止

### 2.应该如何处理异常

- 异常处理技术使我们可以将错误代码从主逻辑中移出，使程序更清晰，能增强程序可维护性
- 我们可以有选择地处理异常：
  - 所有异常
  - 某种特定类型的所有异常
  - 一组相关类型的所有异常（例如属于某个类继承层次体系的异常）
- C++的异常处理机制可以从项目一开始就很容易地设计异常处理

### 3.合适使用异常处理

- 异常处理用于处理同步错误，也就是语句执行时发生的错误
- 常见的适用异常处理的错误有：数组下标越界、算数溢出、被零除、函数参数不合法、内存不够引起的内存分配不成功
- 异常处理不是用于处理异步事件相关的错误，例如：磁盘读写结束、网络信息到达、点击鼠标或键盘，这些与程序的控制流程并行、独立
- 异常处理机制还适用于处理程序与其他软件元素，例如：成员函数、构造函数、析构函数、类交互时出现的问题
  - 这些软件元素通常并不在内部处理错误，而是使用了异常提示程序发生了问题
  - 这就是每个应用程序可以实现个性化的错误处理
- 复杂的
- 当

### 4.异常处理思想

### 5.异常处理语法

- 语法：

  - 抛掷异常的程序段

    - ...
    - `throw 表达式;`
    - ...

  - 捕获并处理异常的程序段

    - ```c++
      try
          复合语句	//保护段
      catch (异常声明)
          复合语句	//异常处理机制
      catch (异常声明)
          复合语句
      ```

- 解释：

  - 若有异常则通过`throw`创建应该异常对象并抛掷
  - 将可能抛出异常的程序段嵌在`try`之中。通过正常的顺序执行到达`try`语句，然后执行`try`块内部的保护段
  - 如果再保护段执行期间没有引起异常，那么跟在`try`块后的`catch`子句就不执行、程序从`try`块后的最后一个`catch`子句后面的语句继续执行
  - `catch`子句按其在`try`块后出现的顺序被检查。匹配的`catch`子句将捕获并处理异常或继续抛掷异常，或部分处理然后继续抛掷
  - 如果匹配的处理器未找到，则库函数`<terminate>`将自动调用，其默认是调用`abort`终止程序

- 示例：

  - ```c++
    #include<iostream>
    #include<string>
    using namespace std;
    
    int divide(int x, int y)
    {
    	if (y == 0)
    		throw x;
    	return x / y;
    }
    
    int main()
    {
    	try
    	{
    		cout << "5 / 2 = " << divide(5, 2) << endl;
    		cout << "8 / 0 = " << divide(8, 0) << endl;
    		cout << "7 / 1 = " << divide(7, 1) << endl;
    	}
    	catch (int e)
    	{
    		cout << e << " is divided by zero!" << endl;
    	}
    
    	system("pause");
    	return 0;
    }
    ```

### 6.异常声明（异常规范 ， Exception specification）

- 一个函数显式声明可能抛出的异常，有利于函数调用者为异常处理做好准备

- 可以在函数声明中列出这个函数可能抛掷出的所有异常类型，例如：

  - ```c++
    void fun() throw(A, B, C, D)
    ```

- 若无异常接口声明，则此函数可以抛掷任何类型的异常

- 不抛掷任何类型异常的函数声明如下：

  - ```c++
    void fun() throw();
    或
    void fun() noexcept;
    ```

- 对明确不会抛出异常的函数使用`noexcept`说明符修饰

  - 异常护理使编译和运行有额外开销，省去异常处理可以优化加速调用
  - 需保持该函数内部调用函数和定义语句均不会抛出异常的一致性

- 配套有`noexcept`运算符，可判断函数是否使用了`noexcept`说明

  - ```c++
    void f() noexcept;
    noexcept(f());	//返回true，说明f有noexcept说明
    ```

- 慎用异常声明的情况：

  - 对于带类型参数的函数模板，要尽量避免使用异常声明，因为不同类型对于相同行为的定义不同，抛出的异常也就不同，因而函数模板很难或不可能确定它具现化实体所可能抛出的异常
  - 使用回调（callback）函数时
  - 系统可能抛出的异常

# 二阶段案例：职工管理系统

## （一）管理系统需求

- 职工管理系统可以用来管理公司内所有员工的信息，本教程主要利用C++来实现一个基于多态的职工管理系统
- 公司中职工分为三类：普通员工、经理、老板
  - 显示信息时，需要显示：职工编号、职工姓名、职工岗位、以及职责
    - 普通员工职责：完成经理交给的任务
    - 经理职责：完成老板交给的任务，并下发任务给员工
    - 老板职责：管理公司所有职务
  
- 管理系统中需要实现的功能如下：
  1. 退出管理程序：退出当前管理系统
  2. 增加职工信息：实现批量添加职工功能，将信息录入到文件中，职工信息为：职工编号、姓名、部门编号
  3. 显示职工信息：显示公司内部所有职工信息
  4. 删除离职员工：按照编号删除指定职工
  5. 修改职工信息：按照编号修改职工信息
  6. 查找职工信息：按照职工的编号或职工的姓名进行查找相关的人员信息
  7. 按照编号排序：按照职工编号进行排序，排序规则由用户指定
  8. 清空所有文档：清空文件中所有职工信息（清空前需要在此确认，防止误删）

## （二）创建项目

- 创建新项目
- 添加文件

## （三）创建管理类

- 管理类负责的内容如下：
  - 与用户沟通的菜单界面
  - 对职工增删改查的操作
  - 与文件的读写交互

### 1.创建文件

- 在头文件和原文件的文件下分别创建`workManager.h`和`workManager.cpp`文件

### 2.头文件实现

- 在`workManager.h`中设计管理类

- 代码实现：

  - ```c++
    #pragma once		//防止头文件重复包含
    #include<iostream>
    using namespace std;
    
    class WorkerManager
    {
    public:
    	WorkerManager();	//构造，头文件只声明，不实现
    	~WorkerManager();	//析构，头文件只声明，不实现
    };
    ```


### 3.源文件实现

- 在`workManager.cpp`中将构造函数和析构函数空实现补全

- 代码实现：

  - ```c++
    #include"workerManager.h"
    
    WorkerManager::WorkerManager()	//构造函数，cpp文件中实现
    {
    
    }
    
    WorkerManager::~WorkerManager()	//析构函数，cpp文件中实现
    {
    
    }
    ```


## （四）菜单功能

- 功能描述：与用户的沟通界面

### 1.添加成员函数

- 在管理类`workManger.cpp`中添加函数`void Show_Menu();`

### 2.菜单功能实现

- 在`workManager.h`中提供菜单功能的成员函数`void Show_Menu();`

- 在`workManger.cpp`中实现函数`void Show_Menu();`

- 代码实现：

  - ```c++
    void WorkerManager::Show_Menu()	//菜单功能
    {
    	cout << "********************************" << endl;
    	cout << "****** 欢迎使用职工管理系统 ******" << endl;
    	cout << "******** 0.退出管理系统 ********"  << endl;
    	cout << "******** 1.增加职工信息 ********" << endl;
    	cout << "******** 2.显示职工信息 ********" << endl;
    	cout << "******** 3.删除离职职工 ********" << endl;
    	cout << "******** 4.修改职工信息 ********" << endl;
    	cout << "******** 5.查找职工信息 ********" << endl;
    	cout << "******** 6.按照编号排序 ********" << endl;
    	cout << "******** 7.清空所有文档 ********" << endl;
    }
    ```


### 3.测试菜单功能

- 在`职工管理系统.cpp`中测试菜单功能

- 代码实现：

  - ```c++
    int main()
    {
    	WorkerManager wm;	//实例化管理者对象
    	wm.Show_Menu();	//调用展示菜单
    
    
    	system("pause");
    	return 0;
    }
    ```


## （五）退出功能

### 1.提供功能接口

- 在main函数中提供分支选择，提供每个功能接口

- 代码实现：

  - ```c++
    int main()
    {
    	WorkerManager wm;	//实例化管理者对象
    	int choice = 0;
    	while (1)
    	{
    		wm.Show_Menu();	//调用展示菜单
    		cout << "请输入您的选择：" << endl;
    		cin >> choice;
    		switch (choice)
    		{
    		case 0:	//退出系统
    			break;
    		case 1:	//添加职工
    			break;
    		case 2:	//显示职工
    			break;
    		case 3:	//删除职工
    			break;
    		case 4:	//修改职工
    			break;
    		case 5:	//查找职工
    			break;
    		case 6:	//排序职工
    			break;
    		case 7:	//清空文件
    			break;
    		default:
    			system("cls");	//清空屏幕
    			break;
    		}
    	}
    
    	system("pause");
    	return 0;
    }
    ```


### 2.实现退出功能

- 在`workManager.h`中提供退出系统的成员函数`void exitSystem();`

- 在`workManager.cpp`中提供具体的功能实现

- 代码实现：

  - ```c++
    void WorkerManager::exitSystem()
    {
    	cout << "欢迎下次使用!" << endl;
    	system("pause");
    	exit(0);	//无论在哪里调用，程序都可以直接退出
    }
    ```

- 关键点：

  - ```c++
    exit(0);	//无论在哪里调用，程序都可以直接退出
    ```


### 3.测试功能

- 在main函数分支0选项中，调用退出程序的接口

## （六）创建职工类

### 1.创建职工抽象类

- 职工的分类：普通员工、经理、老板

- 将三种职工抽象到一个类（worker）中，利用多态管理不同职工种类

- 职工的属性：职工编号、职工姓名、职工所在部门编号

- 职工的行为：岗位职责信息描述、获取岗位名称

- 头文件文件夹下，创建头文件`worker.h`的文件

- 代码实现：

  - ```c++
    #pragma once
    #include<iostream>
    #include<string>
    using namespace std;
    
    class Worker		//抽象职工基类
    {
    public:
    	//职工行为
    	virtual void showInfo() = 0;		//展示个人信息（纯虚函数）
    	virtual string getDepyName() = 0;	//获取岗位信息（纯虚函数）
    
    	//职工属性
    	int m_Id;	//职工编号
    	string m_Name;	//职工姓名
    	int m_DeptId;	//职工所在部门名称编号
    };
    ```


### 2.创建普通员工类

- 普通员工类继承职工抽象类，并重写父类中纯虚函数

- 在头文件和源文件的文件夹下分别创建`employee.h`和`employee.cpp`文件

- 代码实现：

  - `employee.h``：

    - ```c++
      //普通员工文件
      #pragma once
      #include<iostream>
      #include<string>
      #include"worker.h"
      using namespace std;
      
      class Employee :public Worker	//普通员工类，继承自抽象职工基类，并重写父类中纯虚函数
      {
      public:
      	Employee(int id, string name, int dId);	//有参构造函数声明（传入职工编号，姓名，部门编号）
      
      	void showInfo();	//显示个人信息
      
      	string getDeptName();	//获取岗位信息
      };
      ```

  - ``employee.cpp`：

    - ```c++
      #include"employee.h"
      
      Employee::Employee(int id, string name, int dId)	//有参构造函数声明（传入职工编号，姓名，部门编号）
      {
      	this->m_Id = id;
      	this->m_Name = name;
      	this->m_DeptId = dId;
      	//形参名与成员变量名一样时必须加this指针，不一样时可加可不加
      }
      
      void Employee::showInfo()	//显示个人信息
      {
      	cout << "职工编号：" << this->m_Id
      		<< "\t职工姓名：" << this->m_Name
      		<< "\t岗位：" << this->getDeptName()	//获取岗位信息
      		<< "\t岗位职责：完成经理交给的任务" << endl;
      }
      
      string Employee::getDeptName()	//获取岗位信息
      {
      	return string("员工");
      }
      ```


### 3.创建经理类

- 经理类继承职工抽象类，并重写父类中纯虚函数，和普通员工类似

- 在头文件和源文件的文件夹下分别创建`manager.h`和`manager.cpp`文件

- 代码实现：

  - `manager.h``：

    - ```c++
      //经理文件
      #pragma once
      #include<iostream>
      #include<string>
      #include"worker.h"	
      using namespace std;
      
      class Manager :public Worker	//经理类，继承自抽象职工基类，并重写父类中纯虚函数
      {
      public:
      	Manager(int id, string name, int dId);	//有参构造函数声明（传入职工编号，姓名，部门编号）
      
      	void showInfo();	//显示个人信息
      
      	string getDeptName();	//获取岗位信息
      };
      ```

  - ``manager.cpp`：

    - ```c++
      #include"manager.h"
      
      Manager::Manager(int id, string name, int dId)	//有参构造函数声明（传入职工编号，姓名，部门编号）
      {
      	this->m_Id = id;
      	this->m_Name = name;
      	this->m_DeptId = dId;
      }
      
      void Manager::showInfo()	//显示个人信息
      {
      	cout << "职工编号：" << this->m_Id
      		<< "\t职工姓名：" << this->m_Name
      		<< "\t岗位：" << this->getDeptName()	//获取岗位信息
      		<< "\t岗位职责：完成老板交给的任务，并且下发任务给普通员工" << endl;
      }
      
      string Manager::getDeptName()	//获取岗位信息
      {
      	return string("经理");
      }
      ```


### 4.创建老板类

- 老板类继承职工抽象类，并重写父类中纯虚函数，和普通员工类似

- 在头文件和源文件的文件夹下分别创建`boss.h`和`boss.cpp`文件

- `boss.h``

  - ```c++
    //老板文件
    #pragma once
    #include<iostream>
    #include<string>
    #include"worker.h"	
    using namespace std;
    
    class Boss :public Worker	//老板类，继承自抽象职工基类，并重写父类中纯虚函数
    {
    public:
    	Boss(int id, string name, int dId);	//有参构造函数声明（传入职工编号，姓名，部门编号）
    
    	void showInfo();	//显示个人信息
    
    	string getDeptName();	//获取岗位信息
    };
    ```

- ``boss.cpp`

  - ```c++
    #include"boss.h"
    
    Boss::Boss(int id, string name, int dId)	//有参构造函数声明（传入职工编号，姓名，部门编号）
    {
    	this->m_Id = id;
    	this->m_Name = name;
    	this->m_DeptId = dId;
    }
    
    void Boss::showInfo()	//显示个人信息
    {
    	cout << "职工编号：" << this->m_Id
    		<< "\t职工姓名：" << this->m_Name
    		<< "\t岗位：" << this->getDeptName()	//获取岗位信息
    		<< "\t岗位职责：管理公司所有事务" << endl;
    }
    
    string Boss::getDeptName()	//获取岗位信息
    {
    	return string("总裁");
    }
    ```


### 5.测试多态

- 在`职工管理系统.cpp`中添加测试函数，并且运行能够产生多态

- 代码实现：

  - ```c++
    //普通员工类测试代码
    	Worker* worker;	//多态：父类指针指向子类对象，一个接口有多种形态，由于创建对象不同，显示的对象也不一样
    	worker = new Employee(1, "aaa", 1);	//创建一个普通员工
    	worker->showInfo();	//显示个人信息
    	delete worker;
    
    	worker = new Manager(2, "bbb", 2);	//创建一个经理
    	worker->showInfo();	
    	delete worker;
    
    	worker = new Boss(3, "ccc", 3);	//创建一个老板
    	worker->showInfo();
    	delete worker;
    ```


## （七）添加职工

- 功能描述：批量添加职工，并且保存到文件中

### 1.功能分析

- 分析：
  - 用户在批量创建时，可能会批量创建不同种类的职工
  - 如果想将所有不同种类的员工都放到一个数组中，可以将所有员工的指针维护到同一个数组里
  - 如果想在程序里维护这个不定长的数组，可以将数组创建到堆区，并利用`Worker **`的指针维护

### 2.功能实现

- 在`WorkerManager.h`头文件中添加成员属性：

  - ```c++
    int m_EmpNum;	//记录文件中的人数个数
    Worker** m_EmpArray;	//员工数组的指针	
    ```

  - `new出来的员工类型是用worker*类型的指针指向;而要new一个存放worker*类型数据的数组，则要用worker** 类型的指针指向`

- 在`WorkerManager()`构造函数中初始化属性：

  - ```c++
    this->m_EmpNum = 0;	//初始化人数为0
    this->m_EmpArray = NULL;	//初始化数组指针为空
    ```

- 在`WorkerManager.h`头文件中添加成员函数：

  - ```c++
    void Add_Emp();	//添加职工
    ```

- 在`WorkerManager.cpp`中实现该函数：

  - ```c++
    void WorkerManager::Add_Emp()		//添加职工
    {
    	cout << "请输入添加职工的数量" << endl;
    	int addNum;	//保存用户的输入数量
    	cin >> addNum;
        //判断输入数据是否有效，大于零则有效，否则提示输入有误
    	if (addNum > 0)	
    	{
    		//添加思路是在堆区开辟一块新的数组内存空间，大小等于原职工数量加新添加的职工数量，将原数组内容移动到新数组，在后面继续添加新职工，添加完成后释放原数组空间，成员函数数组指针指向新的内存空间，更新职工数量
            int newSize = this->m_EmpNum + addNum;	//计算新空间的大小，等于原数量加新添加的数量
    		Worker** newSpace = new Worker*[newSize];	//开辟新空间
    		if (this->m_EmpArray != NULL)	//判断数组是否为空（？？？不理解），若不为空，则将原数组内容移动到新数组
    		{
    			for (int i = 0; i < this->m_EmpNum; i++)	//拷贝数组原有内容
    			{
    				newSpace[i] = this->m_EmpArray[i];	//（？？？）这样就可以拷贝吗
    			}
    		}
    		for (int i = 0; i < addNum; i++)	//批量添加数据
    		{
    			int id;	//职工编号
    			string name;	//姓名
    			int dSelect;	//部门编号
    			cout << "请输入第" << i + 1 << "个员工的职工编号:" << endl;
    			cin >> id;
    			cout << "请输入该员工的姓名:" << endl;
    			cin >> name;
    			cout << "请选择该职工的岗位：" << endl;
    			cout << "1.普通员工" << endl;
    			cout << "2.经理" << endl;
    			cout << "3.老板" << endl;
    			cin >> dSelect;
    			Worker* worker = NULL;
    			switch (dSelect)
    			{
    			case 1:
    				worker = new Employee(id, name, 1);
    				break;
    			case 2:
    				worker = new Manager(id, name, 2);
    				break;
    			case 3:
    				worker = new Boss(id, name, 3);
    				break;
    			default:
    				break;
    			}
    			newSpace[this->m_EmpNum + i] = worker;	//新加入的这个职工在数组中的位置是this->m_EmpNum + i
    		}
    		delete[] this->m_EmpArray;	//释放原有数组
    		this->m_EmpArray = newSpace;	//更改职工数组的指向，指向新建数组的首地址
    		this->m_EmpNum = newSize;	//更新职工的数量
             this->m_FileIsEmpty = false;	//更新文件为非空状态（在文件操作时需要用到的标志）
    		cout << "成功添加" << addNum << "名新职工" << endl;
    	}
    	else
    	{
    		cout << "输入数据有误" << endl;
    	}
    	//按任意键清屏
    	system("pause");
    	system("cls");
    }
    
    ```

  - 在`~WorkManager()`析构函数中释放堆区数据

    - ```c++
      WorkerManager::~WorkerManager()	//析构函数，cpp文件中实现
      {
      	//释放堆区数据
      	if (this->m_EmpArray)	
      	{
      		delete[] this->m_EmpArray;
      		this->m_EmpArray = NULL;
      	}
      }
      
      ```


### 3.测试添加

## （八）文件交互 - 写文件

- 功能描述：对文件进行读写
  - 在上一个添加功能中，我们只是将所有数据添加到了内存中，一旦程序结束就无法保存，因此文件管理类需要一个与文件进行交互的功能，对于文件进行读写操作

### 1.设定文件路径

- 在`workerManger.h`中添加宏常量，并且包含头文件`<fstream>`

- ```c++
  #include<fstream>
  #define FILENAME "empFile.txt"
  ```

### 2.成员函数声明

- 在`workerManger.h`中添加成员函数`void save();`

### 3.保存文件功能实现

- ```c++
  void WorkManager::Save()
  {
      ofstream ofs;	//创建流对象
      ofs.open(FILENAME,ios::out);	//打开方式
      for(int i=0;i<this->m_EmpNum;i++)
      {
          ofs << this->m_EmpArray[i]->m_Id << " "
              << this->m_EmpArray[i]->m_Name << " "
              <<this->m_EmpArray[i]->m_DeptId << endl;
      }
      ofs.close();	//关闭文件
  }
  ```

### 4.保存文件功能测试

## （九）文件交互 - 读文件

- 功能描述：
  - 将文件中的内容读到程序中；
- 虽然我们实现了添加职工后保存到文件的操作，但是每次开始运行程序，并没有将文件中的数据读取到程序中，而我们的程序中还有清空文件的需求。因此构造函数初始化数据的情况分为三种：
  1. 第一次使用：文件未创建
  2. 文件存在但数据为空
  3. 文件存在且保存职工数据

### 1.文件未创建

- 在`workerManger.h`中添加新的成员属性`m_FileIsEmpty`标志文件是否为空

  - ```c++
    bool m_FileIsEmpty;	//标志文件是否为空
    ```

- 修改`workerManager.cpp`中构造函数代码

  - ```c++
    WorkerManager::WorkerManager()	//构造函数，cpp文件中实现
    {
    	ifstream ifs;
        ifs.open(FILENAME , ios::in);
        
        //文件不存在的情况
        if(!ifs.is_open())	//如果文件打开失败，返回0，取反为1
        {
            cout << "文件不存在" << endl;
            this->m_EmpNum = 0;	//初始化人数为0
            this->m_FileIsEmpty = true;	//初始化文件为空标志
            this->m_EmpArray = NULL;	//初始化数组指针为空
            ifs.close();
            return;
        }
    }
    ```


### 2.文件存在但数据为空

- 在`workerManager.cpp`中的构造函数追加代码

  - ```c++
    //文件存在，但记录为空的情况
    char ch;
    ifs >> ch;	//读入文件中的一个字符，若文件为空，则读入的是EOF（？？？不太理解）
    if(ifs.eof())	//判断读入是否为EOF，若是，则为真
    {
        cout << "文件为空！" << endl;
        this->m_EmpNum = 0;	//初始化人数为0
        this->m_FileIsEmpty = true;	//初始化文件为空标志
        this->m_EmpArray = NULL;	//初始化数组指针为空
        ifs.close();
        return;
    }
    ```

- 成功添加职工后，需要修改文件空标志为假，在成员函数`void WorkerManager::Add_Emp()	`中添加：

  - ```c++
    this->m_FileIsEmpty = false;	//更新文件为非空状态
    ```


### 3.文件存在且保存职工数据

- 获取记录的职工人数：
  - 在`workerManger.h`中添加新的成员函数`int get_EmpNum();`
  
    - ```c++
      int get_EmpNum();	//获取文件中的职工人数
      ```
  
  - 在`workerManger.cpp`中实现成员函数`int WorkerManager::get_EmpNum()`
  
    - ```c++
      int WorkerManager::get_EmpNum()
      {
          ifstream ifs;	//创建读文件流
          ifs.open(FILENAME,ios::in);	//打开文件，为读文件打开
          
          int id;
          string name;
          int dId;
          
          int num = 0;	//统计人数
          
          while(ifs >> id && ifs >> name && ifs >> dId)	//成功读完一个人的数据，num就可以加1
          {
              num++;
          }
          
          if.close();	//关闭文件
          return num;    
      }
      ```
  
- 初始化数组：
  - 根据职工数据以及职工数据，初始化`workerManger`中的`Worker** m_EmpArray`指针
  
  - 在`workerManger.h`中添加新的成员函数`void init_Emp();`
  
    - ```c++
      void init_Emp();	//初始化职工数组
      ```
  
  - 在`workerManger.cpp`中实现成员函数`void WorkerManager::init_Emp()`
  
    - ```c++
      void WorkerManager::init_Emp()
      {
          ifstream ifs;	//创建读文件流
          ifs.open(FILENAME,ios::in);	//打开文件，为读文件打开
          
          int id;
          string name;
          int dId;
          
          int index = 0;	//用作数组下标
      	while(ifs >> id && ifs >> name && ifs >> dId)	//成功读完一个人的数据
          {
              Worker* worker = NULL;	//挨个临时储存每个职工
              //根据不同部门创建不同对象
              if(dId == 1)	//普通职工
              {
                  worker = new Employee(id, name, 1);
              }
              else if(dId == 2)	//经理
              {
                   worker = new Manager(id, name, 2);
              }
              else	//总裁
              {
                   worker = new Boss(id, name, 3);
              }
              //存到数组中
              this->m_EmpArray[index] = worker;
              index++;	//数组下标++
          }
      }
      ```
  
- 在`workerManager.cpp`中的构造函数追加代码：

  - ```c++
    //文件存在，且记录数据
    	int num = this->get_EmpNum();
    	cout << "职工人数为：" << num << endl;
    
    	//初始化修改职工人数
    	this->m_EmpNum = num;	
    
    	//初始化修改职工数组
    	this->m_EmpArray = new Worker*[this->m_EmpNum];	//该步骤应该是动态分配数组内存大小
    	this->init_Emp(); //初始化职工数组（将文件中的职工信息放到堆区申请的职工数组中，便于程序执行）
    
    	//初始化修改文件空标志为非空
    	this->m_FileIsEmpty = false;
    
    	//这里应该是测试
    	//输出数组中职工信息，测试是否从文件中正确读取
    	//这里也可以调用worker的三个子类的showInfo()函数，因为在初始化数组往worker**数组中创建新对象的时候就已经分类识别不同对象了，所有可以利用多态显示职工信息
    	for (int i = 0; i < this->m_EmpNum; i++)
    	{
    		cout << "职工编号：" << this->m_EmpArray[i]->m_Id
    			<< "\t职工姓名：" << this->m_EmpArray[i]->m_Name
    			<< "\t部门编号：" << this->m_EmpArray[i]->m_DeptId << endl;
    	}
    	for (int i = 0; i < this->m_EmpNum; i++)
    	{
    		this->m_EmpArray[i]->showInfo();
    	}
    ```


## （十）显示职工

- 功能描述：
  - 显示当前所有职工信息

### 1.显示职工函数声明

- 在`workerManger.h`中添加新的成员函数`void Show_Emp();`

  - ```c++
    void Show_Emp();	//添加新的成员函数
    ```


### 2.显示职工函数实现

- 在`workerManager.cpp`中实现成员函数`void WorkerManagerShow_Emp()`

  - ```c++
    void WorkerManager::Show_Emp()
    {
        //判断文件空标志是否为空
        if(this->m_FileIsEmpty)
        {
            cout << "文件不存在或记录为空！" << endl;
        }
        else
        {
            for (int i = 0; i < this->m_EmpNum; i++)
    		{
    			this->m_EmpArray[i]->showInfo();
    		}
        }
        system("pause");
        system("cls");
    }
    ```


### 3.测试显示职工功能

## （十一）删除职工

- 功能描述：
  - 按照职工编号进行删除职工操作

### 1.删除职工函数声明

- 在`workerManager.h`中添加成员函数`void Del_Emp;`

  - ```c++
    void Del_Emp();	//删除职工
    ```

### 2.职工是否存在函数声明

- 后续很多功能都需要根据职工是否存在来进行操作，如：删除职工、修改职工、查找职工

- 因此单独再添加一个判断职工是否存在的函数

- 在`workerManager.h`中添加成员函数`int IsExist(int id);`

  - ```c++
    //根据职工编号判断职工是否存在，若存在返回职工在数组中的位置，不存在则返回-1
    int IsExist(int id);	//判断职工是否存在
    ```

### 3.职工是否存在函数实现

- 在`workerManager.cpp`中实现成员函数`int WorkerManager::IsExist(int id)`

  - ```c++
    int WorkerManager::IsExist(int id)
    {
        for(int i = 0; i < this->m_EmpNum; i++)
        {
            if(this->m_EmpArray[i]->m_Id == id)	//若找到了这个编号，返回数组下标
            {
                return i;            
            }
        }
        return -1;
    }
    ```

### 4.删除职工函数实现

- 在`workerManager.cpp`中实现成员函数`void WorkerManager::Del_Emp()`

  - ```c++
    void WorkerManager::Del_Emp()
    {
    	//先判断文件是否为空
    	if (this->m_FileIsEmpty)
    	{
    		cout << "文件不存在或文件为空！" << endl;
    	}
    	else
    	{
    		cout << "请输入要删除的职工编号：" << endl;
    		int id = 0;
    		cin >> id;
    		int index = this->IsExist(id);	//判断该职工是否存在，返回其数组下标
    		if (index == -1)	//若该职工不存在
    		{
    			cout << "删除失败，该职工不存在！" << endl;
    		}
    		else
    		{
    			//数组数据前移覆盖
    			for (int i = index; i < this->m_EmpNum - 1; i++)
    			{
    				this->m_EmpArray[i] = this->m_EmpArray[i + 1];
    			}
    			this->m_EmpNum--;	//职工总人数减一
    			this->save();	//更新保存文件
    			cout << "删除成功！" << endl;
    		}
    	}
    	//删除成功后按任意键继续并清屏
    	system("pause");
    	system("cls");
    }
    ```

### 5.测试删除职工

## （十二）修改职工

- 功能描述：
  - 按照编号修改职工信息

### 1.修改职工函数声明

- 在`workerManager.h`中添加成员函数`void Mod_Emp();`

  - ```c++
    void Mod_Emp();	//修改职工
    ```

### 2.修改职工函数实现

- 在`workerManager.cpp`中实现成员函数`void WorkerManager::Mod_Emp()`

  - ```c++
    void WorkerManager::Mod_Emp()
    {
    	//先判断文件是否为空
    	if (this->m_FileIsEmpty)
    	{
    		cout << "文件不存在或文件为空！" << endl;
    	}
    	else
    	{
    		cout << "请输入修改的职工编号：" << endl;
    		int id;
    		cin >> id;
    		int index = this->IsExist(id);	//判断该职工是否存在，返回其数组下标
    		if (index == -1)	//若该职工不存在
    		{
    			cout << "修改失败，该职工不存在！" << endl;
    		}
    		else
    		{
    			delete this->m_EmpArray[index];	//为什么要delete，直接修改替换不可以吗？ 因为修改职工后对象可能会改变，不是简单的修改内容
    			int newId = 0;
    			string newName = "";
    			int dSelect = 0;
    			cout << "查到了编号为" << id << "的职工，请输入新的职工编号：" << endl;
    			cin >> newId;
    			cout << "请输入新的职工姓名：" << endl;
    			cin >> newName;
    			cout << "请输入新的岗位：" << endl;
    			cout << "1.普通职工" << endl;
    			cout << "2.经理" << endl;
    			cout << "3.老板" << endl;
    			cin >> dSelect;
    			Worker* worker = NULL;
    			if (dSelect == 1)
    			{
    				worker = new Employee(newId, newName, 1);
    			}
    			else if (dSelect == 2)
    			{
    				worker = new Manager(newId, newName, 2);
    			}
    			else if (dSelect == 3)
    			{
    				worker = new Boss(newId, newName, 3);
    			}
    			else
    			{
    				cout << "输入错误！" << endl;
    			}
    			this->m_EmpArray[index] = worker;	//更新到数组中
    			cout << "修改成功!" << endl;
    			this->save();	//保存到文件中
    		}
    	}
    	//删除成功后按任意键继续并清屏
    	system("pause");
    	system("cls");
    }
    ```

### 3.测试修改职工功能

## （十三）查找职工

- 功能描述：
  - 按照职工的编号或职工的姓名进行查找相关的人员信息

### 1.查找职工函数声明

- 在`workerManager.h`中添加成员函数`void Find_Emp();`

  - ```c++
    void Find_Emp();	//查找职工
    ```


### 2.查找职工函数实现

- 在`workerManager.cpp`中实现成员函数`void WorkerManager::Find_Emp()`

  - ```c++
    //查找职工
    void WorkerManager::Find_Emp()
    {
    	//先判断文件是否为空
    	if (this->m_FileIsEmpty)
    	{
    		cout << "文件不存在或文件为空！" << endl;
    	}
    	else
    	{
    		cout << "请选择查找的方式：" << endl;
    		cout << "1.按照职工编号查找" << endl;
    		cout << "2.按照职工姓名查找" << endl;
    
    		int select = 0;
    		cin >> select;
    
    		if (select == 1)
    		{
    			int id;
    			cout << "请输入要查找的职工编号：" << endl;
    			cin >> id;
    			int index = this->IsExist(id);
    			if (index != -1)
    			{
    				cout << "查找成功！该职工的信息如下：" << endl;
    				this->m_EmpArray[index]->showInfo();	//多态实现的显示职工信息
    			}
    			else
    			{
    				cout << "查找失败!该职工不存在" << endl;
    			}
    		}
    		else if (select == 2)
    		{
    			string name;
    			cout << "请输入要查找的职工姓名：" << endl;
    			cin >> name;
    			bool flag = false;	//用于标志是否找到，默认为flase
    			int num = 0;	//用于记录重名情况下一共有几人重名
    			for (int i = 0; i < this->m_EmpNum; i++)
    			{
    				if (name == this->m_EmpArray[i]->m_Name)
    				{
    					cout << "查找成功！该职工信息如下：" << endl;
    					this->m_EmpArray[i]->showInfo();
    					flag = true;
    					num++;
    				}
    			}
    			if (num>1)
    			{
    				cout << "有重名情况，该姓名的职工有" << num << "位" << endl;
    			}
    			if (flag == false)
    			{
    				cout << "查找失败！该职工不存在!" << endl;
    			}	
    		}
    		else
    		{
    			cout << "输入错误，请重新输入" << endl;
    		}	
    	}
    	//删除成功后按任意键继续并清屏
    	system("pause");
    	system("cls");
    }
    ```

### 3.测试查找职工功能

## （十四）排序

- 功能描述：
  - 按照职工编号进行排序，排序规则由用户指定
    - 按职工编号升序
    - 按职工编号降序

### 1.排序函数声明

- 在`workerManager.h`中添加成员函数`void Sort_Emp();`

  - ```c++
    void Sort_Emp();	//排序
    ```

### 2.排序函数实现

- 在`workerManager.cpp`中实现成员函数`void WorkerManager::Find_Emp()`

  - ```c++
    void WorkerManager::Sort_Emp()
    {
    	//先判断文件是否为空
    	if (this->m_FileIsEmpty)
    	{
    		cout << "文件不存在或文件为空！" << endl;
    	}
    	else
    	{
    		cout << "请选择排序方式：" << endl;
    		cout << "1.按职工编号升序" << endl;
    		cout << "2.按职工编号降序" << endl;
    		int select = 0;
    		cin >> select;
    		if (select == 1)	//升序
    		{
    			Worker* worker = NULL;
    			for (int i = 0; i < this->m_EmpNum - 1; i++)	//n个数需要冒泡排序n-1趟
    			{
    				bool flag = false;	//用于标志一趟排序中是否发生了交换，若未发生交换说明已经排序成功，结束循环
    				for (int j = 0; j < this->m_EmpNum - 1 - i; j++)	//每次交换都可以将一个最大数或最小数移动到其应该在的位置，所有每次需要比较的数都减一
    				{
    					if (this->m_EmpArray[j]->m_Id > this->m_EmpArray[j + 1]->m_Id)
    					{
    						worker = this->m_EmpArray[j];
    						this->m_EmpArray[j] = this->m_EmpArray[j + 1];
    						this->m_EmpArray[j + 1] = worker;
    						flag = true;
    					}
    				}
    				if (!flag)
    					break;
    			}
    		}
    		else if (select == 2)	//降序
    		{
    			Worker* worker = NULL;
    			for (int i = 0; i < this->m_EmpNum - 1; i++)	//n个数需要冒泡排序n-1趟
    			{
    				bool flag = false;	//用于标志一趟排序中是否发生了交换，若未发生交换说明已经排序成功，结束循环
    				for (int j = 0; j < this->m_EmpNum - 1 - i; j++)	//每次交换都可以将一个最大数或最小数移动到其应该在的位置，所有每次需要比较的数都减一
    				{
    					if (this->m_EmpArray[j]->m_Id < this->m_EmpArray[j + 1]->m_Id)
    					{
    						worker = this->m_EmpArray[j];
    						this->m_EmpArray[j] = this->m_EmpArray[j + 1];
    						this->m_EmpArray[j + 1] = worker;
    						flag = true;
    					}
    				}
    				if (!flag)
    					break;
    			}
    		}
    		else
    		{
    			cout << "输入错误！" << endl;
    		}
    		this->Show_Emp();	//输出排序后的职工
    		this->save();	//更新保存文件
    	}		
    	//排序成功后按任意键继续并清屏
    	system("pause");
    	system("cls");
    }
    
    ```

### 3.测试排序功能

## （十五）清空文件

- 功能描述：
  - 将文件中记录数据清空

### 1.清空函数声明

- 在`workerManager.h`中添加成员函数`void Clean_File();`

  - ```c++
    void Clean_File();	//清空文件
    ```

### 2.清空函数实现

- 在`workerManager.cpp`中实现成员函数`void WorkerManager::Clean_File()`

  - ```c++
    //清空文件
    void WorkerManager::Clean_File()
    {
    	cout << "请再次确认是否要清空文件：" << endl;
    	cout << "1.确定" << endl;
    	cout << "2.取消" << endl;
    	int select = 0;
    	cin >> select;
    	if (select == 1)
    	{
    		ofstream ofs;
    		ofs.open(FILENAME, ios::trunc);	//打开方式为：删除文件后重新创建
    		//也可直接写成：ofstream ofs(FILENAME, ios::trunc);、
    		ofs.close();
    		//释放堆区数据，打开文件的时候构造函数在堆区开辟的空间（析构函数功能不全，且执行析构函数的时候有判断条件，不会重复释放）
    		if (this->m_EmpArray)
    		{
    			for (int i = 0; i < this->m_EmpNum; i++)
    			{
    				if (this->m_EmpArray[i])	//判断每一个数组中每一个对象是否有在堆区开辟空间，如果有，则逐个释放
    				{
    					delete this->m_EmpArray[i];
    					this->m_EmpArray[i] = NULL;
    				}
    			}
    			delete[] this->m_EmpArray;
    			this->m_EmpArray = NULL;
    			this->m_EmpNum = 0;	//职工个数归零
    			this->m_FileIsEmpty = true;	//文件空标志置为空
    		}
    	}
    	system("pause");
    	system("cls");
    }
    ```

### 3.测试清空函数

- ```c++
  case 7:	
          wm.Clean_File();//清空文件
          break;
  ```

# 三.C++提高编程

- 本阶段主要针对C++泛式编程和STL技术作详细探讨，探讨C++更深层的使用

## （一）模板

### 1.模板的概念

- 模板就是使用通用的模具，大大提高复用性
- 模板的特点：
  - 模板不可以直接使用，它只是一个框架
  - 模板的通用并不是万能的

### 2.函数模板

- C++另一种编程思想称为**泛式编程**，主要利用技术就是**模板**
- C++提供两种模板机制：**函数模板** 和 **类模板**

#### （1）函数模板语法

- 函数模板作用：建立一个通用函数，其函数返回值类型和形参类型可以不具体制定，用一个虚拟的类型来代表

- 语法：

  - ```c++
    template<typename T>
    //函数声明或定义
    ```

- 解释：

  - `template` --- 声明创建模板
  - `typename` --- 表面其后面的符号是一种数据类型，可以用`class`代替
  - `T` --- 通用的数据类型，名称可以替换，通常为大写字母

- 总结：

  - 函数模板利用关键字`template`
  - 使用函数模板有两种方式：自动类型推导、显式指定类型
  - 模板的目的是为了提高复用性，将类型参数化
  
- 示例：

  - ```c++
    #define _CRT_SECURE_NO_WARNINGS
    #include<iostream>
    #include<string>
    using namespace std;
    
    //函数模板
    template<typename T>	//声明一个模板，告诉编译器后面的T不要报错，T是一个通用数据类型
    void mySwap(T &a, T &b)
    {
    	T temp = a;
    	a = b;
    	b = temp;
    }
    
    //交换两个整型
    void swapInt(int &a, int &b)
    {
    	int temp = a;
    	a = b;
    	b = temp;
    }
    
    //交换两个浮点型数
    void swapDouble(double &a, double &b)
    {
    	double temp = a;
    	a = b;
    	b = temp;
    }
    
    void test01()
    {
    	int a = 10;
    	int b = 20;
    
    	//swapInt(a, b);	//普通函数
    	//下面使用函数模板交换，有两种方式
    	//1.自动类型推导
    	//mySwap(a, b);	//可以达到与函数swapInt一样的效果
    	//2.显式指定类型
    	mySwap<int>(a, b);
    
    	cout << "a = " << a << endl;
    	cout << "b = " << b << endl;
    
    	double c = 0.5;
    	double d = 2.5;
    
    	//swapDouble(c, d);	//普通函数
    	//mySwap(c, d);
    	mySwap<double>(c, d);
    
    	cout << "c = " << c << endl;
    	cout << "d = " << d << endl;
    
    }
    
    int main() 
    {
    	test01();
    
    	system("pause");
    	return 0;
    }
    ```
  

#### （2）函数模板注意事项

- 注意事项：
  - 自动类型推导，必须推导出一致的数据类型 T，才可以使用
  - 模板必须要确定出 T 的数据类型，才可以使用
  
- 示例：

  - ```c++
    #define _CRT_SECURE_NO_WARNINGS
    #include<iostream>
    #include<string>
    using namespace std;
    
    //函数模板注意事项
    template<class T>	//typename可以替换称为class
    void mySwap(T &a, T &b)
    {
    	T temp = a;
    	a = b;
    	b = temp;
    }
    
    //1.自动类型推导，必须推导出一致的数据类型 T，才可以使用
    void test01()
    {
    	int a = 10;
    	int b = 20;
    	char c = 'c';
    	//mySwap(a, b);	//正确
    	//mySwap(a, c);	//错误
    	cout << "a = " << a << endl;
    	cout << "b = " << b << endl;
    }
    //2.模板必须要确定出 T 的数据类型，才可以使用
    template<class T>	
    void func()
    {
    	cout << "func调用" << endl;
    }
    
    void test02()
    {
    	//func();	//报错
    }
    
    int main() 
    {
    	test01();
    
    	system("pause");
    	return 0;
    }
    ```

- 总结：
  - 使用模板时必须确定出通用数据类型T，并且能够推导出一致的类型

#### （3）函数模板案例

- 案例描述：
  - 利用函数模板封装一个排序的函数，可以对不同的数据类型数组类型排序
  - 排序规则从大到小，排序算法为选择排序
  - 分别利用`char`数组和`int` 数组进行测试
  
- 示例：

  - ```c++
    #define _CRT_SECURE_NO_WARNINGS
    #include<iostream>
    #include<string>
    using namespace std;
    
    //从大到小
    template<class T>
    void mySort(T arr[], int len)
    {
    	for (int i = 0; i < len; i++)
    	{
    		int max = i;	//默认当前未排序部分的第一个为最大值
    		for (int j = i; j < len; j++)
    		{
    			if (arr[j] > arr[max])
    			{
    				max = j;
    			}
    		}	//一轮循环可找到未排序部分的最大值
    		if(max != i)
    		{
    			T temp = arr[i];
    			arr[i] = arr[max];
    			arr[max] = temp;
    		}
    	}
    }
    
    //打印数组模板
    template<class T>
    void printArray(T arr[], int len)
    {
    	for (int i = 0; i < len; i++)
    	{
    		cout << arr[i] << " ";
    	}
    	cout << endl;
    }
    
    void test01()
    {
    	//测试char数组
    	char arr[] = "dcbafegijkh";
    	int num = sizeof(arr) / sizeof(char);
    	mySort(arr, num);
    	printArray(arr, num);
    }
    
    void test02()
    {
    	//测试int数组
    	int arr[] = { 0, 8, 7, 6, 5, 3, 4, 2, 10 };
    	int num = sizeof(arr) / sizeof(int);
    	mySort(arr, num);
    	printArray(arr, num);
    }
    
    int main() 
    {
    	test01();
    	test02();
    
    	system("pause");
    	return 0;
    }
    ```


#### （4）普通函数和函数模板的区别

- 普通函数和函数模板的区别：
  - 普通函数调用时可以发生自动类型转换（隐式类型转换）
  - 函数模板调用时，如果利用自动类型推导，不会发生隐式类型转换
  - 如果显式指定类型的方式，可以发生隐式类型转换
  
- 示例：

  - ```c++
    #define _CRT_SECURE_NO_WARNINGS
    #include<iostream>
    #include<string>
    using namespace std;
    
    //普通函数
    int myAdd01(int a, int b)
    {
    	return a + b;
    }
    
    template<typename T>
    T myAdd02(T a, T b)
    {
    	return a + b;
    }
    
    void test01()
    {
    	int a = 10;
    	int b = 20;
    	char c = 'c';
    	//调用普通函数
    	cout << myAdd01(a, b) << endl;
    	cout << myAdd01(a, c) << endl;	//可以运行，发生隐式类型转换，c转化成它对应的ASCII码
    
    	///调用模板函数
    	cout << myAdd02(a, b) << endl;
    	//cout << myAdd02(a, c) << endl;	//报错，函数模板调用时，如果利用自动类型推导，不会发生隐式类型转换
    	cout << myAdd02<int>(a, c) << endl;	//可以运行，如果显式指定类型的方式，可以发生隐式类型转换，指定int后，可以发生隐式类型转换
    }
    
    int main() 
    {
    	test01();
    
    	system("pause");
    	return 0;
    }
    ```

- 总结：
  - 建议使用显式指定类型的方法，调用函数模板，因为可以自己确定通用类型

#### （5）普通函数和函数模板的调用规则

- 调用规则：

  1. 如果函数模板和普通函数都可以实现，则优先调用普通函数
  2. 
  3. 可以通过空模板参数列表来强制调用函数模板
  4. 函数模板也可以发生重载
  5. 如果函数模板可以产生更多的匹配，优先调用函数模板

- 示例：

  - ```c++
    #define _CRT_SECURE_NO_WARNINGS
    #include<iostream>
    #include<string>
    using namespace std;
    
    //普通函数和函数模板的调用规则
    //1. 如果函数模板和普通函数都可以实现，则优先调用普通函数
    //2. 可以通过空模板参数列表来强制调用函数模板
    //3. 函数模板也可以发生重载
    //4. 如果函数模板可以产生更多的匹配，优先调用函数模板
    
    void myPrint(int a, int b)
    {
    	cout << "调用普通函数" << endl;
    }
    
    template<class T>
    void myPrint(T a, T b)	//与普通函数同名
    {
    	cout << "调用模板" << endl;
    }
    
    template<class T>
    void myPrint(T a, T b, T c)	//模板重载
    {
    	cout << "调用重载模板" << endl;
    }
    
    void test01()
    {
    	int a = 10;
    	int b = 20;
    	//myPrint(a, b);	//如果函数模板和普通函数都可以实现，则优先调用普通函数
    
    	
    	myPrint<>(a, b);	//可以通过空模板参数列表来强制调用函数模板
    	int c = 30;
    	myPrint(a, b, c);	//函数模板也可以发生重载
    
    	char c1 = 'a';
    	char c2 = 'b';
    	myPrint(c1, c2);	//普通函数也可强制类型类型转换、不会报错，但函数模板可以产生更多的匹配，优先调用函数模板
    }
    
    int main() 
    {
    	test01();
    
    	system("pause");
    	return 0;
    }
    ```
  
- 总结：

  - 如果提供了函数模板，最好就不要再提供普通函数，否则容易出现二义性

#### （6）模板的局限性

- 局限性：	

  - 模板的通用性并不是万能的

- 示例：

  - ```c++
    #define _CRT_SECURE_NO_WARNINGS
    #include<iostream>
    #include<string>
    using namespace std;
    
    //模板的局限性
    
    class Person
    {
    public:
    	Person(string name, int age)
    	{
    		this->m_Name = name;
    		this->m_Age = age;
    	}
    
    	string m_Name;
    	int m_Age;
    };
    
    template<class T>
    bool myCompare(T &a, T &b)
    {
    	if(a == b)
    	{
    		return true;
    	}
    	return false;
    }
    
    //利用具体化Person的版本实现代码，具体化优先使用
    template<> bool myCompare(Person &p1, Person &p2)
    {
    	if (p1.m_Name == p2.m_Name && p1.m_Age == p2.m_Age)
    	{
    		return true;
    	}
    	return false;
    }
    
    void test01()
    {
    	int a = 10;
    	int b = 20;
    	bool result = myCompare(a, b);
    	if (result)
    	{
    		cout << "a == b" << endl;
    	}
    	else
    	{
    		cout << "a != b" << endl;
    	}
    }
    
    void test02()	//未具体化时会报错
    {
    	Person p1("Tom", 10);
    	Person p2("Tom", 10);
    
    	bool result = myCompare(p1, p2);
    	if (result)
    	{
    		cout << "p1 == p2" << endl;
    	}
    	else
    	{
    		cout << "p1 != p2" << endl;
    	}
    }
    
    int main() 
    {
    	test01();
    	test02();
    
    	system("pause");
    	return 0;
    }
    ```

- 总结：

  - 利用具体化的模板，可以解决自定义类型的通用化
  - 学习模板并不是为了写模板，而是再STL能够运用系统提供的模板

### 3.类模板

#### （1）类模板语法

- 类模板作用：
  - 建立一个通用类：类中的成员数据类型可以不具体制定，用一个虚拟的类型来代表

- 语法：
  - ```c++
    template<typename T>
    类
    ```

- 解释：

  - template  ---  声明创建模板
  - typename  ---  表明其后面的符号是一种数据类型，可以用`class`代替
  - T  ---  通用数据类型，名称可以替换，通常为大写字母

- 示例：

  - ```c++
    #define _CRT_SECURE_NO_WARNINGS
    #include<iostream>
    #include<string>
    using namespace std;
    
    //类模板
    template<class NameType,class AgeType>
    class Person
    {
    public:
    	Person(NameType name, AgeType age)
    	{
    		this->m_Name = name;
    		this->m_Age = age;
    	}
    
    	void showPerson()
    	{
    		cout << "name:" << this->m_Name << endl;
    		cout << "age:" << this->m_Age << endl;
    	}
    
    	NameType m_Name;
    	AgeType m_Age;
    };
    
    void test01()
    {
    	Person<string, int> p1("aaa", 100);
    	p1.showPerson();
    }
    
    int main() 
    {
    	test01();
    
    	system("pause");
    	return 0;
    }
    ```

- 总结：

  - 类模板与函数模板语法类似，在声明模板`template`后面加类，此类称为类模板

#### （2）类模板与函数模板区别

- 类模板和函数模板区别主要有两点：

  - 类模板没有自动类型推导的使用方式
  - 类模板在模板参数列表中可以有默认参数

- 示例：

  - ```c++
    #define _CRT_SECURE_NO_WARNINGS
    #include<iostream>
    #include<string>
    using namespace std;
    
    //类模板和函数模板的区别:
    //1. 类模板没有自动类型推导的使用方式
    //2. 类模板在模板参数列表中可以有默认参数
    template<class NameType,class AgeType = int>
        
    class Person
    {
    public:
    	Person(NameType name, AgeType age)
    	{
    		this->m_Name = name;
    		this->m_Age = age;
    	}
    
    	void showPerson()
    	{
    		cout << "name:" << this->m_Name << endl;
    		cout << "age:" << this->m_Age << endl;
    	}
    
    	NameType m_Name;
    	AgeType m_Age;
    };
    
    void test01()
    {
    	//Person p1("aaa", 100);	//报错，类模板没有自动类型推导的使用方式
    	Person<string, int> p1("aaa", 100);	//正确，必须使用显式指定类型
    	p1.showPerson();
    }
    
    void test02()
    {
    	Person<string> p2("bbb", 200);	//类模板在模板参数列表中可以有默认参数，默认AgeType类型为int,实例化时就可以省略
    	p2.showPerson();
    }
    
    int main() 
    {
    	test01();
    	test02();
    
    	system("pause");
    	return 0;
    }
    ```

#### （3）类模板中成员函数的创建时机

- 类模板中成员函数与普通类中成员函数创建时机是有区别的：

  - 普通类中的成员函数一开始就可以创建
  - 类模板中的成员函数在调用时才创建

- 示例：

  - ```c++
    #define _CRT_SECURE_NO_WARNINGS
    #include<iostream>
    #include<string>
    using namespace std;
    
    class Person1
    {
    public:
    
    	void showPerson1()
    	{
    		cout << "Person1 show" << endl;
    	}
    };
    
    class Person2
    {
    public:
    
    	void showPerson2()
    	{
    		cout << "Person2 show" << endl;
    	}
    };
    
    template<class T>
    class MyClass
    {
    public:
    	T obj;
    
    	void func1()
    	{
    		obj.showPerson1();
    	}
    
    	void func2()
    	{
    		obj.showPerson2();
    	}
    };
    
    void test01()
    {
    	MyClass<Person1> m;
    	m.func1();
    	//m.func2();	//报错
    	MyClass<Person2> n;
    	n.func2();
    }
    
    int main() 
    {
    	test01();
    
    	system("pause");
    	return 0;
    }
    ```

#### （4）类模板对象作函数参数

- 学习目标：类模板实例化出的对象，向函数传参的方式

- 一共有三种传入方式：

  1. 指定传入的类型（最常用）  --- 直接显示对象的数据类型
  2. 参数模板化  --- 将对象中的参数变为模板进行传递
  3. 整个类模板化  --- 将这个对象类型模板化进行传递

- 示例：

  - ```c++
    #define _CRT_SECURE_NO_WARNINGS
    #include<iostream>
    #include<string>
    using namespace std;
    
    //类模板对象作函数参数
    //1. 指定传入的类型  --- 直接显示对象的数据类型
    //2. 参数模板化  --- 将对象中的参数变为模板进行传递
    //3. 整个类模板化  --- 将这个对象类型模板化进行传递
    
    template<class T1,class T2>
    class Person
    {
    public:
    	Person(T1 name, T2 age)
    	{
    		this->m_Name = name;
    		this->m_Age = age;
    	}
    
    	void showPerson()
    	{
    		cout << "姓名：" << this->m_Name << " 年龄：" << this->m_Age << endl;
    	}
    
    	T1 m_Name;
    	T2 m_Age;
    };
    
    //1. 指定传入的类型  --- 直接显示对象的数据类型
    void printPerson1(Person<string, int> &p)
    {
    	p.showPerson();
    }
    
    void test01()
    {
    	Person<string, int> p("aaa", 100);
    	printPerson1(p);
    }
    
    //2. 参数模板化  --- 将对象中的参数变为模板进行传递
    template<class T1,class T2>
    void printPerson2(Person<T1,T2> &p)
    {
    	p.showPerson();
    	cout << "T1的类型：" << typeid(T1).name() << endl;
    	cout << "T2的类型：" << typeid(T2).name() << endl;
    }
    
    void test02()
    {
    	Person<string, int> p("bbb", 200);
    	printPerson2(p);
    }
    
    //3. 整个类模板化  --- 将这个对象类型模板化进行传递
    template<class T>
    void printPerson3(T &p)
    {
    	p.showPerson();
    	cout << "T的类型：" << typeid(T).name() << endl;
    }
    
    void test03()
    {
    	Person<string, int> p("ccc", 300);
    	printPerson3(p);
    }
    
    int main() 
    {
    	test01();
    	test02();
    	test03();
    
    	system("pause");
    	return 0;
    }
    ```

#### （5）类模板与继承

- 当类模板要继承时，需要注意以下几点：

  - 当子类继承的父类是一个类模板时，子类在声明时，要指出父类中T的类型
  - 如果不指定，编译器无法给子类分配内存
  - 如果想灵活制定出父类中T的类型，子类也需要变为类模板

- 示例：

  - ```c++
    #define _CRT_SECURE_NO_WARNINGS
    #include<iostream>
    #include<string>
    using namespace std;
    
    //类模板与继承
    
    template<class T>
    class Base
    {
    	T m;
    };
    
    class Son :public Base<int>	//必须要知道父类中的T类型，才能继承给子类
    {
    
    };
    
    //如果想灵活制定出父类中T的类型，子类也需要变为类模板
    template<class T1, class T2>
    class Son2 :public Base<T2>
    {
    public:
    	Son2()
    	{
    		cout << "T1的类型：" << typeid(T1).name() << endl;
    		cout << "T2的类型：" << typeid(T2).name() << endl;
    	}
    
    	T1 obj;
    };
    
    void test01()
    {
    	Son S1;
    }
    
    void test02()
    {
    	Son2<int, char> S2;
    }
    
    int main() 
    {
    	test02();
    
    	system("pause");
    	return 0;
    }
    ```

#### （6）类模板成员函数类外实现

- 示例：

  - ```c++
    #define _CRT_SECURE_NO_WARNINGS
    #include<iostream>
    #include<string>
    using namespace std;
    
    //类模板成员函数类外实现
    template<class T1,class T2>
    class Person
    {
    public:
    	Person(T1 name, T2 age);
    	/*{
    		this->m_Name = name;
    		this->m_Age = age;
    	}*/
    	void shouPerson();
    	/*{
    		cout << "姓名：" << this->m_Name << " 年龄：" << this->m_Age << endl;
    	}*/
    
    	T1 m_Name;
    	T2 m_Age;
    };
    
    //构造函数类外实现
    template<class T1, class T2>
    Person<T1, T2>::Person(T1 name, T2 age)
    {
    this->m_Name = name;
    this->m_Age = age;
    }
    
    //成员函数类外实现
    template<class T1, class T2>
    void Person<T1, T2>::shouPerson()
    {
    cout << "姓名：" << this->m_Name << " 年龄：" << this->m_Age << endl;
    }
    
    void test01()
    {
    	Person<string, int> p1("aaa", 100);
    	p1.shouPerson();
    }
    
    int main() 
    {
    	test01();
    
    	system("pause");
    	return 0;
    }
    ```

- 总结：

  - 类模板中成员函数类外实现时，需要加上模板参数列表

#### （7）类模板分文件编写

- 学习目标：

  - 掌握类模板成员函数分文件编写产生的问题以及解决方式

- 问题：

  - 类模板中成员函数创建时机是在调用阶段，导致分文件编写时链接不到

- 解决：

  - 解决方法1：直接包含.cpp文件（不常用）

    - 将类的声明放在 .h 文件中，将成员函数实现放在 .cpp 文件中，正常是包含 .h 文件，但这里必须直接包含 .cpp 文件

  - 解决方式2：（常用）

    - 将声明和实现写到同一个文件中，并更改后缀名为.hpp，hpp是一般约定名称，不是强制

    - .hpp 文件：

      - ```c++
        #define _CRT_SECURE_NO_WARNINGS
        #include<iostream>
        #include<string>
        using namespace std;
        
        template<class T1, class T2>
        class Person
        {
        public:
        	Person(T1 name, T2 age);
        	
        	void shouPerson();
        	
        	T1 m_Name;
        	T2 m_Age;
        };
        
        template<class T1, class T2>
        Person<T1, T2>::Person(T1 name, T2 age)
        {
        	this->m_Name = name;
        	this->m_Age = age;
        }
        
        template<class T1, class T2>
        void Person<T1, T2>::shouPerson()
        {
        	cout << "姓名：" << this->m_Name << " 年龄：" << this->m_Age << endl;
        }
        ```

#### （8）类模板与友元

- 学习目标：

  - 掌握类模板配合友元函数的类内和类外实现

- 全局函数类内实现：直接在类内声明友元即可

- 全局函数类外实现：需要提前让编译器知道全局函数的存在

- 示例：

  - ```c++
    #define _CRT_SECURE_NO_WARNINGS
    #include<iostream>
    #include<string>
    using namespace std;
    
    //通过全局函数打印Person信息
    
    //提前让编译器知道Person类存在
    template<class T1, class T2>
    class Person;
    
    template<class T1, class T2>
    void printPerson2(Person<T1, T2> p)
    {
    	cout << "类外实现---姓名：" << p.m_Name << " 类外实现---年龄：" << p.m_Age << endl;
    }
    
    template<class T1, class T2>
    class Person
    {
    	//全局函数 类内实现（？？？）
    	friend void printPerson(Person<T1,T2> p)
    	{
    		cout << "姓名：" << p.m_Name << " 年龄：" << p.m_Age << endl;
    	}
    
    	//全局函数 类外实现（？？？）
    	//加空模板参数列表
    	//如果全局函数是类外实现，需要让编译器提前知道这个函数存在
    	friend void printPerson2<>(Person<T1, T2> p);
    
    public:
    	Person(T1 name, T2 age)
    	{
    		this->m_Name = name;
    		this->m_Age = age;
    	}
    
    	void shouPerson();
    private:
    	T1 m_Name;
    	T2 m_Age;
    };
    
    //全局函数类内实现测试
    void test01()
    {
    	Person<string, int> p("aaa", 10);
    	printPerson(p);
    }
    
    //全局函数类外实现测试
    void test02()
    {
    	Person<string, int> p2("bbb", 20);
    	printPerson2(p2);
    }
    
    int main() 
    {
    	test01();
    	test02();
    
    	system("pause");
    	return 0;
    }
    ```

- 总结：

  - 建议使用类内实现

#### （9）类模板案例

- 案例描述：实现一个通用的数组类，要求如下：

  - 可以对内置数据类型以及自定义数据类型的数据进行存储
  - 将数组中的数据存储到堆区
  - 构造函数中可以传入数组的容量
  - 提供对应的拷贝构造函数以及operator=防止浅拷贝问题
  - 提供尾插法和尾删法对数组中的数据进行增加和删除
  - 可以通过下标的方式访问数组中的元素
  - 可以获取数组中当前元素个数和容量

- 代码：

  - ```c++
    
    
    ```

  - 

## （二）STL初识

## （三）STL - 常用容器

### 1.string容器

### 2.vector容器

### 3.

### 4.

### 5.

### 6.

### 7.

### 8.

### 9.

### 10.

## （四）STL - 函数对象

## （五）STL - 常用算法

#  三阶段综合大案例：机房预约系统

## （1）机房预约系统需求

## （2）创建项目

## （3）创建主菜单

## （4）退出功能实现

## （5）创建身份类

## （6）登录模块

## （7）管理员模块

## （8）学生模块

## （9）教师模块

# C++常见报错解决方案

## 1.无法指定数组的显式初始值设定项？

- 报错原因：
  - .h头文件中不能进行私有成员数组的初始化，尝试在.cpp 文件中初始化数据。
- 解决方案：
  - 将`float frequencies[5] = {90,45,22.5,11.25,5.625};`写到.h文件中都会报这样的错误
  - 所以只能在.h文件中仅仅声明它：`float frequencies[5];`
  - 然后在对应的.cpp文件中对其进行初始化

## 2.0xC00000FD:Stack overflow溢出分析

- 报错原因：
  - 设置c++程序的堆栈空间解决栈溢出问题。在我们自己定义结构体时，往往会包含很多数组，在创建包含大数组的类（或数据）时，栈就会发生溢出，从而在刚刚调试进入函数体中，就会报错Stack Overflow错误。往往是程序还没运行算法呢，就down掉了，这是由于系统分配给程序的栈空间太小。而此时把定义的结构体变量定成全局变量可以避免这个问题，但是终究不是解决问题的最好方法。
- 解决方法：
  - 方法1：修改vs系统分配栈的大小
  - 方法2： 动态创建
  - 方法3：如果不需要特别多数据，可以将数组大小设置小一些（只适合小项目）

# 杂类

## 1.求当前系统时间

- ```c++
  #define _CRT_SECURE_NO_WARNINGS
  #include<iostream>
  #include<string>
  #include<ctime>
  using namespace std;
  
  int main() 
  {
  	// 获取当前时间
  	time_t t = time(0);
  	tm* now = localtime(&t);
  
  	// 提取年月日
  	int year = now->tm_year + 1900;   // 年份是从1900年开始的
  	int month = now->tm_mon + 1;      // 月份范围是0-11
  	int day = now->tm_mday;
  
  	string time = to_string(year) + "-" + to_string(month) + "-" + to_string(day);
  
  	cout << time << endl;
  
  	system("pause");
  	return 0;
  }
  ```

## 2.C/C++中string和int相互转换的常用方法

- 通过 `std::to_string() `函数转换

  - ```c++
    #include <iostream>
    using namespace std;
    int main()
    {
        int num = 123;
        std::cout << to_string(num);
        return 0;
    }
    ```

## 3.修改默认堆栈大小

- 可避免数组过大或递归过多导致栈溢出报错或程序崩溃的问题（不知道描述是否正常）
- 项目 -> 属性 -> 链接器 -> 系统 -> 堆栈保留大小（默认为1MB = 1024*1024）将其修改更大

## 4.字符串指针

- ```c++
  #include <iostream>
  
  class Integer
  {
  private:
  	int value;
  
  public:
  	// 构造函数
  	Integer(int val = 0)
  	{
  		value = val;  // 在构造函数的函数体内进行初始化
  	}
  
  	// 拷贝构造函数
  	Integer(const Integer &other)
  	{
  		value = other.value;  // 在构造函数的函数体内进行初始化
  	}
  
  	// 打印值的方法
  	void print(const char *prefix = nullptr) const	//字符串指针，且有初始化
  	{
  		if (prefix != nullptr)
  		{
  			std::cout << prefix;	//可以达到要求的输出效果
  		}
  		std::cout << value << std::endl;
  	}
  
  	// 加法运算符重载
  	Integer operator+(int other) const
  	{
  		return Integer(value + other);
  	}
  
  	// 减法运算符重载
  	Integer operator-(const Integer &other) const
  	{
  		return Integer(value - other.value);
  	}
  
  	// 乘法赋值运算符重载
  	void operator*=(const Integer &other)
  	{
  		value *= other.value;
  	}
  };
  
  int main()
  {
  	// 创建Integer的实例
  	Integer a(2), b = a, c;
  
  	// 打印值
  	a.print("a=");  // 输出: a=2
  	b.print("b=");  // 输出: b=2
  	c.print();      // 输出: 0（默认值）
  
  	// 使用加法运算符重载
  	c = b + 1;
  	b.print("b=");  // 输出: b=2
  	c.print("c=");  // 输出: c=3
  
  	// 使用减法运算符重载
  	c = a - c;
  	a.print("a=");  // 输出: a=2
  	c.print("c=");  // 输出: c=-1
  
  	// 使用乘法赋值运算符重载
  	c *= b;
  	c.print("Finally,c=");  // 输出: Finally,c=-2
  
  	return 0;
  }
  
  class C
  {
  	int &c;
  public:
  	C(){ c = 0; }
  };
  ```

- 

# 常用或可能用到的英文

- implement   实现
- maintain   维护
- programming styles   程序设计风格
- programming paradigms   程序设计范式
- abstraction   抽象
- algorithm   算法
- computation   计算
- expressions   表达式
- literals   字面值
- portability   可移植性
- aggregate   集合
- arbitrary   任意的
- attributes
- arguments   参数
