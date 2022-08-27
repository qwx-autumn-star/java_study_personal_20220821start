#jAVA
>>>>>


@java基础

java的版本分为javaSE，javaEE，javaME：
	javaSE是java的基础版，是java的基础与核心，主要用于桌面应用程序的开发。
	javaEE是java的企业版，主要用于开发企业级分布式的网络程序。
	javaME主要应用于嵌入式系统开发，包括手机等（已经落后了）。

java语言特性：简单，面向对象，分布性，可移植性，解释性，安全性，健壮性，多线程，高性能，动态。

java严格区分大小写。

文件名与主类名相同，含有main（）方法的类称为主类，每一个应用程序中必须包含一个main（）方法，一个类只能有一个 main() 方法。

类层面（类体）上的变量称为类的全局变量/类的成员变量，方法的方法体中的变量称为局部变量。

public static void mian（String[] args）{}必须声明为public static void，main（）方法是程序执行的入口。

java 语言支持两种数据类型，分别是基本数据类型和引用数据类型，其中 null 是一种特殊的引用数据类型的关键字，表示“空”的意思，是绝对意义上的空，这个空指的是不存在。"" 表示的是一个长度为 0 的空字符串，它在内存中会被分配一个空间。

java基本数据类型（8种）：
	数值型：整数类型（byte，short，int，long），浮点类型（float，double）
	字符型（char）
	布尔型（boolean）

数据类型相关（8位为一字节）：
	byte   8位  -2^7~2^7-1
	short  16位 -2^15~2^15-1
	int    32位 -2^31~2^31-1
	long   64位 -2^63~2^63-1
	float  32位 -1.4E-45~3.4028235E38
	double 64位 -4.9E-324~1.7976931348623157E308
	char   16位 转义字符（\开头）
	boolean     不能与整数类型进行转换 

机器层面上 1bit 表示 1比特位，比如按位计算等就是以此为单位。1byte占用8bit，在unicode编码下，1char占用2byte。 （按顺序可以理解为 bit（比特位） 组成 byte（字节） 组成 char（字符））

单精度float类型值的正确写法为 值f 或 值f ,双精度double类型值的正确写法为 值D 或 值d ，小数默认不写被认为是双精度值。

标识符是用来标识类名，变量名，方法名，数组名，文件名的有效字符序列。

标识符可以由字母，下划线，美元符号和数字组成，并且第一个字符不能是数字，不能是java中的关键字。

java语言使用unicode标注字符集。

java关键字有：
	int public this finally boolean abstract
	continue float long short throw throws 
	return break for static new interface 
	strictfp package super void try switch
	else catch implements private final class
	extends volatile while synchronized instanceof char
	protected import transient dafault double if
	default byte do case
保留字：
	goto const
特殊直接变量：
	true false null

常量为成员变量时，必须在定义时设定初值。

类体中的变量为成员变量，在整个类中有效，分为静态变量和实例变量；类的方法体中定义的变量（方法{}之间）为局部变量，只在当前的方法体中有效；局部变量和成员变量同名时，成员变量被隐藏。

局部变量没有默认值，局部变量不允许使用访问控制修饰符（public、private 和 protected）和 static 修饰符修饰。

不建议使用类似 a=b=c=10； 这种形式的语句。

三元运算符 条件式?值1:值2，true值1，否则值2。

运算符优先级尽量使用括号运算符避免错误。

隐式类型转换是数据的低级类型向高级类型转换，系统会自动执行，其中不包含逻辑类型和字符类型；低取值范围的数据类型和高取值范围的数据类型一同运算时，会隐式类型转换为高取值范围的数据类型。

显式类型转换是高精度变量的值赋给低精度变量的变量（又称为强制类型转换）且必须进行转换，当把整数赋值给byte，short，int，long类型变量时，如果超出了取值范围，也必须进行转换，格式为：
	（类型名）要转换的值 

a+=1 相当于 a=（a的数据类型）（a+1） ，发生了显式类型转换。	

代码注释：
	单行注释 //
	多行注释 /* */
	文档注释 /** */ 
		/**注释内容*/

		/**
		*注释内容
		*/

		/**
		注释内容
		*/
	多行注释中可以嵌套单行注释，但不可以嵌套多行注释

	javadoc标记（文档注释）：
		类注释 一般必须放在所有的“import”语句之后，类定义之前。一个类注释的创建人、创建时间和描述是不可缺少的。
		eg：（模板）
			@projectName（项目名称）: project_name
			@package（包）: package_name.file_name
			@className（类名称）: type_name
			@description（类描述）: 一句话描述该类的功能
			@author（创建人）: user 
			@createDate（创建时间）: datetime  
			@updateUser（修改人）: user 
			@updateDate（修改时间）: datetime
			@updateRemark（修改备注）: 说明本次修改内容
			@version（版本）: v1.0

		方法注释 必须紧靠在方法定义的前面，主要声明方法参数、返回值、异常等信息。除了可以使用通用标签外，还可以使用下列的以@开始的标签
		eg：（模板）
		    @param 变量描述：对当前方法的参数部分添加一个说明，可以占据多行。一个方法的所有 @param 标记必须放在一起
		    @return 返回类型描述：对当前方法添加返回值部分，可以跨越多行
		    @throws 异常类描述：表示这个方法有可能抛出异常

		字段注释 在定义字段的前面，用来描述字段的含义。
		eg：
			/**用户名*/
			public String name;

代码风格（初步）：
	普遍单行
	非必要，不空格

switch（expr）中，在java5以前，expr只能是byte、short、char、int，从java5开始，java中引入了枚举类型，expr也可以是enum类型，从java7开始，expr还可以是字符串（String），但是在目前所有的版本中expr都不可以是长整型（long）,浮点数（float，double）。

直接量是指在程序中通过源代码直接给出的值，例如在int a = 5;代码中，为变量 a 所分配的初始值 5 就是一个直接量。

foreach（jdk5+）：
	for(类型 变量名:集合) {语句块;}

return break contiue：
	return 关键字并不是专门用于结束循环的，return 语句用于终止函数的执行或退出类的方法，并把控制权返回该方法的调用者。如果这个方法带有返回类型，return 语句就必须返回这个类型的值；如果这个方法没有返回值，可以使用没有表达式的 return 语句。

	break 用于完全结束一个循环，跳出循环体。不管是哪种循环，一旦在循环体中遇到 break，系统将完全结束该循环，开始执行循环之后的代码。
		在 java 中，break 语句有 3 种作用，分别是：在 switch 语句中终止一个语句序列、使用 break 语句直接强行退出循环和使用 break 语句实现 goto 的功能。 

	continue 语句是跳过循环体中剩余的语句而强制执行下一次循环，其作用为结束本次循环，即跳过循环体中下面尚未执行的语句，接着进行下一次是否执行循环的判定。
		continue 语句类似于 break 语句，但它只能出现在循环体中。它与 break 语句的区别在于：continue 并不是中断循环语句，而是中止当前迭代的循环，进入下一次的迭代。简单来讲，continue 是忽略循环语句的当次循环。

		continue 语句只能用在 while 语句、for 语句或者 foreach 语句的循环体之中，在这之外的任何地方使用它都会引起语法错误。

		默认情况下，continue 只会跳出最近的内循环，如果要跳出外循环，可以为外循环添加一个标签 label1，然后使用continue label，这样当条件满足执行 continue 语句时，程序就会跳转出label1:指定的外循环。
			continue //不带标签
			continue label //带标签，label是标签名

如果 main 方法的多行代码之间没有任何流程控制，则程序总是从上向下依次执行，排在前面的代码先执行，排在后面的代码后执行。

在实际开发中，服务器端应用程序通常采用三层体系架构，分别为表现层（web）、持久层（dao）、业务逻辑层（service）。

常用的MVC设计模式一般指MVC框架，V（View）指视图层，M（Model）指数据模型层，C（Controller）指控制层。

一个汉字等于一个字符，字符是 char 。一个汉字等于二个字节，字节是 byte 。 

在面向对象的编程中，大多数复杂操作都会被分解成一系列方法调用。这是因为实现更好的可重用性，将每个可重用的代码单元定义成方法，将复杂任务逐渐分解为更易管理的小型子任务。由于一个大的业务功能需要由多个对象来共同实现，在最终编程模型中，很多对象将通过一系列方法调用来实现通信，执行任务。

boolean类型只有两个直接值:true和false。流程控制语句中的条件判断也必须是boolean类型值，即不能以-1，0或1之类的数字代替。

除成员变量会有默认初始值外，其他变量必须在第一次使用之前初始化。同时boolean作为成员变量时，是没有初始值的，要先赋值才能操作,但是不赋值也不会报错。boolean作为全局变量时，可以不赋值，它的默认值为0。

java中常见的输出函数：
	printf 主要继承了C语言中 printf 的一些特性，可以进行格式化输出。
	print 就是一般的标准输出，但是不换行。
	println 和 print 基本没什么差别，就是最后会换行。

通过引用类型变量来访问所引用对象的属性和方法时，java 虚拟机将采用以下绑定规则：
	动态绑定：
		实例方法与引用变量实际引用的对象的方法进行绑定，这种绑定属于动态绑定，因为是在运行时由 java 虚拟机动态决定的。例如，animal.eat() 是将 eat() 方法与 Cat 类绑定。
	静态绑定：
		静态方法与引用变量所声明的类型的方法绑定，这种绑定属于静态绑定，因为是在编译阶段已经做了绑定。例如，Animal.staticEat() 是将 staticEat() 方法与 Animal 类进行绑定。
		成员变量（包括静态变量和实例变量）与引用变量所声明的类型的成员变量绑定，这种绑定属于静态绑定，因为在编译阶段已经做了绑定。例如，Animal.name 和 Animal.staticName 都是与 Animal 类进行绑定。

方法的形参和实参具有以下特点：
    形参变量只有在被调用时才分配内存单元，在调用结束时，即刻释放所分配的内存单元。因此，形参只有在方法内部有效，方法调用结束返回主调方法后则不能再使用该形参变量。
    实参可以是常量、变量、表达式、方法等，无论实参是何种类型的量，在进行方法调用时，它们都必须具有确定的值，以便把这些值传送给形参。因此应预先用赋值、输入等办法使实参获得确定值。
    实参和形参在数量、类型和顺序上应严格一致，否则会发生“类型不匹配” 的错误。
    方法调用中发生的数据传送是单向的，即只能把实参的值传送绐形参，而不能把形参的值反向地传送给实参。因此在方法调用过程中，形参的值发生改变，而实参中的值不会变化。

堆是用来存放由 new 创建的对象和数组，即动态申请的内存都存放在堆区。栈是用来存放在方法中定义的一些基本类型的变量和对象的引用变量。

==比较引用数据类型的位置是否是同一个和比较基本数据类型的值是否相同，equals（）是Object类中就拥有的，具体要看是否重写了和重写成怎样的方法。

@@


@类和对象

java的三大特征：封装，继承，多态（多态性体现在父类中定义的属性和方法被子类继承后，可以具有不同的属性或表现方式）。java是面向对象编程的，面向对象的三大特性：可重用性，可扩展性，可管理性。

修饰权限符：
	public：共有访问。对所有的类都可见（同类，同包，子类，其他包）。
    protected：保护型访问。对同一个包可见，对不同的包的子类可见（同类，同包，子类）。
    friendly：默认访问权限。只对同一个包可见，注意对不同的包的子类不可见（同类，同包）。
    private：私有访问。只对同一个类可见，其余都不可见（同类）。

    远近关系的权限限制上，同类<同包<子类<其他包。
    在 java 中能够影响到访问权限的只有 private、public、protected、friendly 这几个关键字。

this关键字：
	this 可以代表任何对象，当这个方法被调用时，它所代表的对象才被确定下来，谁在调用这个方法，this 就代表谁。

	this.属性名：
		当一个类的属性（成员变量）名与访问该属性的方法参数名相同时，则需要使用 this 关键字来访问类中的属性，以区分类的属性和方法中的参数。
	this.方法名：
		java 允许对象的一个成员直接调用另一个成员，可以省略 this前缀，即类中方法1调用方法2的形式是方法1调用this.方法2的形式的省略。省略this前缀只是一种假象，虽然程序员省略了调用方法2之前的this，但实际上这个this依然是存在的。
	this（）：
		this（）用来访问本类的构造方法，括号中如果有参数就是调用指定的有参构造方法。this（）不能在普通方法中使用，只能写在构造方法中，并且在构造方法中使用时，必须是第一条语句。

构造方法（构造器）：
	方法名必须与类名相同，可以有 0 个、1 个或多个参数，没有任何返回值，包括 void，默认返回类型就是对象类型本身，只能与 new 运算符结合使用，不要在构造方法里使用 return 来返回当前类的对象，因为构造方法的返回值是隐式的（定义了返回类型或值就会被作为普通方法处理）。

	构造方法不能被 static、final、synchronized、abstract 和 native（类似于 abstract）修饰。构造方法用于初始化一个新对象，所以用 static 修饰没有意义。构造方法不能被子类继承，所以用 final 和 abstract 修饰没有意义。多个线程不会同时创建内存地址相同的同一个对象，所以用 synchronized 修饰没有必要。

	如果在类中没有定义任何一个构造方法，则 java 会自动为该类生成一个默认的构造方法。默认的构造方法不包含任何参数，并且方法体为空。如果类中显式地定义了一个或多个构造方法，则 java 不再提供默认构造方法。无参数的构造方法也被称为 Nullary 构造方法。只有编译程序自动加入的构造方法，才称为默认构造函数。如果自行编写无参数、没有内容的构造函数，就不称为默认构造函数了（只是 Nullary 构造函数）。

对象的销毁：
	在清除对象时，由系统自动进行内存回收，不需要用户额外处理。java 语言的内存自动回收称为垃圾回收（Garbage Collection）机制，简称 GC。垃圾回收机制是指 jVM 用于释放那些不再使用的对象所占用的内存。

	析构方法与构造方法相反，当对象脱离其作用域时（例如对象所在的方法已调用完毕），系统自动执行析构方法。

	对象的引用超过其作用范围或者对象被赋值为 null时对象会被当作垃圾回收。

	在 java 虚拟机的堆区，每个对象都可能处于以下三种状态之一：
		可触及状态：当一个对象被创建后，只要程序中还有引用变量引用它，那么它就始终处于可触及状态。
		可复活状态：当程序不再有任何引用变量引用该对象时，该对象就进入可复活状态。在这个状态下，垃圾回收器会准备释放它所占用的内存，在释放之前，会调用它及其他处于可复活状态的对象的 finalize（） 方法，这些 finalize（） 方法有可能使该对象重新转到可触及状态。
		不可触及状态：当 java 虚拟机执行完所有可复活对象的 finalize（） 方法后，如果这些方法都没有使该对象转到可触及状态，垃圾回收器才会真正回收它占用的内存。
	
	在 java 的 Object 类中还提供了一个 protected 类型的 finalize（） 方法，因此任何 java 类都可以覆盖这个方法，在这个方法中进行释放对象所占有的相关资源的操作。
	具有如下特点：
	    垃圾回收器是否会执行该方法以及何时执行该方法，都是不确定的。
	    finalize() 方法有可能使用对象复活，使对象恢复到可触及状态。
	    垃圾回收器在执行 finalize() 方法时，如果出现异常，垃圾回收器不会报告异常，程序继续正常运行。
	    由于 finalize() 方法的不确定性，所以在程序中可以调用 System.gc() 或者 Runtime.gc() 方法提示垃圾回收器尽快执行垃圾回收操作。调用 System.gc（） 或者 Runtime.gc（） 方法也不能保证回收操作一定执行，它只是提高了 java 垃圾回收器尽快回收垃圾的可能性。

static静态：
	静态变量可以被类的所有实例共享。

	java 中 static 方法不能被覆盖，因为方法覆盖是基于运行时动态绑定的，而 static 方法是编译时静态绑定的。static 方法跟类的任何实例都不相关，所以概念上不适用。

	非静态访问静态既可以标准的通过类名形式，也可以使用不标准的通过对象访问。

	java 语法规定 static 不允许用来修饰局部变量。

	有别于类的 成员变量 和 成员方法 ，static修饰的被称为 类变量 和 类方法 。

	静态变量（类变量）:
	    运行时，java 虚拟机只为静态变量分配一次内存，在加载类的过程中完成静态变量的内存分配。
	    在类的内部，可以在任何方法内直接访问静态变量。
	    在其他类中，可以通过类名访问该类中的静态变量。
	实例变量:
	    每创建一个实例，java 虚拟机就会为实例变量分配一次内存。
	    在类的内部，可以在非静态方法中直接访问实例变量。
	    在本类的静态方法或其他类中则需要通过类的实例对象进行访问。
	静态方法（类方法）与实例方法的区别如下：
		实例方法中可以直接访问所属类的静态变量、静态方法、实例变量和实例方法。
    	静态方法不需要通过它所属的类的任何实例就可以被调用，因此在静态方法中不能使用 this 关键字，也不能直接访问所属类的实例变量和实例方法，但是可以直接访问所属类的静态变量和静态方法。另外，和 this 关键字一样，super 关键字也与类的特定实例相关，所以在静态方法中也不能使用 super 关键字。
    在类中定义静态的属性（类变量），在 main() 方法中可以直接访问，也可以通过类名访问，还可以通过类的实例对象来访问。
    在访问非静态方法时，需要通过实例对象来访问，而在访问静态方法时，可以直接访问，也可以通过类名来访问，还可以通过实例化对象来访问。

    静态代码块指 java 类中的 static{} 代码块，主要用于初始化类，为类的静态变量赋初始值，提升程序性能，静态代码块代码域遵循静态的规则。
    不加 static 的 {} 代码块是非静态代码块，非静态代码块是在创建对象时自动执行的代码，不创建对象不执行该类的非静态代码块，非静态代码块代码域中定义的变量都是局部的，只有域中的代码可以调用。 
    静态代码块特征如下：
	    静态代码块类似于一个方法，但它不可以存在于任何方法体中。
	    静态代码块可以置于类中的任何地方，类中可以有多个静态初始化块。 
	    java 虚拟机在加载类时执行静态代码块，所以很多时候会将一些只需要进行一次的初始化操作都放在 static 代码块中进行。
	    如果类中包含多个静态代码块，则 java 虚拟机将按它们在类中出现的顺序依次执行它们，每个静态代码块只会被执行一次。
	    静态代码块与静态方法一样，不能直接访问类的实例变量和实例方法，而需要通过类的实例对象来访问。

import static静态导入：
	如果一个类中的方法全部是使用 static 声明的静态方法，则在导入时就可以直接使用 import static 的方式导入。
	eg:（模板）
		import static package.ClassName.fieldName|methodName;
		import static package.ClassName.*;

final修饰符:
	使用 final 声明变量时，要求全部的字母大写。
	final变量为常量。
	final方法不可以被重写。
	final类不可以被继承。

	final变量：
    	final 修饰的局部变量必须使用之前被赋值一次才能使用。
    	final 修饰的成员变量在声明时没有赋值的叫“空白 final 变量”。空白 final 变量必须在构造方法或静态代码块中初始化。

    	使用 final 修饰基本类型变量时，不能对基本类型变量重新赋值，因此基本类型变量不能被改变。 
    	使用 final 修饰引用类型变量时，它保存的仅仅是一个引用，final 只保证这个引用类型变量所引用的地址不会改变，即一直引用同一个对象，但这个对象本身完全可以发生改变。

    final方法：
    	不可以被重写，但可以被重载。

    final类：
    	对于 final 类中的成员，可以定义其为 final，也可以不是 final。而对于方法，由于所属类为 final 的关系，自然也就成了 final 型。也可以明确地给 final 类中的方法加上一个 final，这显然没有意义。
    
可变参数:
	eg:（模板）
		methodName({paramlist},paramType…paramName)
			methodName 表示方法名称；paramlist 表示方法的固定参数列表；paramType 表示可变参数的类型；… 是声明可变参数的标识；paramName 表示可变参数名称,可变参数必须定义在参数列表的最后。
		
系统常用包：
	java.lang 	
		java 的核心类库，包含运行 java 程序必不可少的系统类，如基本数据类型、基本数学函数、字符串处理、异常处理和线程类等，系统默认加载这个包
	java.io 	
		java 语言的标准输入/输出类库，如基本输入/输出流、文件输入/输出、过滤输入/输出流等
	java.util 	
		包含如处理时间的 Date 类，处理动态数组的 Vector 类，以及 Stack 和 HashTable 类
	java.awt 	
		构建图形用户界面（GUI）的类库，低级绘图操作 Graphics 类、图形界面组件和布局管理（如 Checkbox 类、Container 类、layoutManger 接口等），以及用户界面交互控制和事件响应（如 Event 类）
	java.awt.image 	
		处理和操纵来自网上的图片的 java 工具类库
	java.wat.peer 	
		很少在程序中直接用到，使得同一个 java 程序在不同的软硬件平台上运行
	java.net 	
		实现网络功能的类库有 Socket 类、ServerSocket 类
	java.lang.reflect 	
		提供用于反射对象的工具
	java.util.zip 	
		实现文件压缩功能
	java.awt.datatransfer 	
		处理数据传输的工具类，包括剪贴板、字符串发送器等
	java.sql 	
		实现 jDBC 的类库
	java.rmi 	
		提供远程连接与载入的支持
	java. security 	
		提供安全性方面的有关支持

递归：
	自己调用自己。
	eg：（简单原理演示）（计算n的阶乘）
		public class factorial {
    	int fact(int n) {
        int result;
        if (n == 1) {
        return 1;   }
        result = fact(n - 1) * n;
        return result;  }      }


@@


@封装、继承和多态

封装：
	特点：
	    只能通过规定的方法访问数据。
	    隐藏类的实例细节，方便修改和实现。
  	实现：
	    修改属性的可见性来限制对属性的访问，一般设为 private。
	    为每个属性创建一对赋值（setter）方法和取值（getter）方法，一般设为 public，用于属性的读写。
	    在赋值和取值方法中，加入属性控制语句（对属性值的合法性进行判断）。

继承：
	类的继承不改变类成员的访问权限，也就是说，如果父类的成员是公有的、被保护的或默认的，它的子类仍具有相应的这些特性，并且子类不能获得父类的构造方法。 

	如果在父类中存在有参的构造方法而并没有重载无参的构造方法，那么在子类中必须含有有参的构造方法，因为如果在子类中不含有构造方法，默认会调用父类中无参的构造方法，而在父类中并没有无参的构造方法，因此会出错。

	java 不支持多继承，只允许一个类直接继承另一个类，即子类只能有一个直接父类，extends 关键字后面只能有一个类名。

	父类中的 private 成员在子类中是不可见的，因此在子类中不能直接使用它们。

	在子类的构造方法中，系统默认第一条是隐藏的调用父类的无参构造方法的super()语句。如果构造方法的第一行代码不是 this() 和 super()，则系统会默认添加 super()。

	优缺点：
		优点：
		    实现代码共享，减少创建类的工作量，使子类可以拥有父类的方法和属性。
		    提高代码维护性和可重用性。
		    提高代码的可扩展性，更好的实现父类的方法。
	    缺点：
		    继承是侵入性的。只要继承，就必须拥有父类的属性和方法。
		    降低代码灵活性。子类拥有父类的属性和方法后多了些约束。
		    增强代码耦合性（开发项目的原则为高内聚低耦合）。当父类的常量、变量和方法被修改时，需要考虑子类的修改，有可能会导致大段的代码需要重构。

super关键字：
	功能：
	    在子类的构造方法中显式的调用父类构造方法：
	    	super(parameter-list)，parameter-list 指定了父类构造方法中的所有参数，super( ) 必须是在子类构造方法的方法体的第一行。
	    访问父类的成员方法和变量：
	    	当子类的成员变量或方法与父类同名时，可以使用 super 关键字来访问。使用 super 访问父类中的成员或方法与 this 关键字的使用相似，只不过它引用的是子类的父类。
	    		super.member
	    		super.function（）

	super和this的区别：
		this 指的是当前对象的引用，super 是当前对象的父对象的引用。

		super 关键字的用法：
		    super.父类属性名：调用父类中的属性
		    super.父类方法名：调用父类中的方法
		    super()：调用父类的无参构造方法
		    super(参数)：调用父类的有参构造方法
		this 关键字的用法：
		    this.属性名：表示当前对象的属性
		    this.方法名(参数)：表示调用当前对象的方法

对象类型转换：
	对象类型转换，是指存在继承关系的对象，不是任意类型的对象。当对不存在继承关系的对象进行强制类型转换时，会抛出 java 强制类型转换（java.lang.ClassCastException）异常。

	向上转型更好的体现了类的多态性，增强了程序的间接性以及提高了代码的可扩展性。当需要用到子类特有的方法时可以向下转型，这也就是为什么要向下转型。

	父类引用指向子类对象为向上转型：
		fatherClass obj = new sonClass();
		向上转型不能使用子类特有的属性和方法，只能引用父类的属性和方法，但是子类重写父类的方法是有效的,向上转型时会优先使用子类中重写父类的方法，向上转型类型会进行自动转换。
	子类引用指向转换为子类类型的父类对象为向下转型：
		sonClass obj = (sonClass) fatherClass;
		向下转型可以调用子类类型中所有的成员，不过需要对父类进行强制类型转换，否则是不安全的，会抛出异常。

	对象的强制类型转换（强制对象类型转换）：
		类型强制转换时想运行成功就必须保证父类引用指向的对象一定是该子类对象，最好使用 instanceof 运算符判断后，再强转。
		如果两种类型之间没有继承关系，那么将不允许进行类型转换。

方法重载：
	如果同一个类中包含了两个或两个以上方法名相同的方法，但形参列表不同，这种情况被称为方法重载（overload）。

	方法重载的要求是两同一不同：同一个类中方法名相同，参数列表不同。至于方法的其他部分，如方法返回值类型、修饰符等，与方法重载没有任何关系。

方法重写（覆盖）：
	在子类中创建了一个与父类中相同名称、相同返回值类型、相同参数列表的方法，只是方法体中的实现不同，以实现不同于父类的功能。

	如果子类中创建了一个成员变量，而该变量的类型和名称都与父类中的同名成员变量相同，我们则称作变量隐藏（父类的变量被隐藏）。

	规则：
	    参数列表必须完全与被重写的方法参数列表相同。
	    返回的类型必须与被重写的方法的返回类型相同（java1.5 版本之前返回值类型必须一样，之后的 java 版本放宽了限制，返回值类型必须小于或者等于父类方法的返回值类型）。
	    访问权限不能比父类中被重写方法的访问权限更低（public>protected>default>private）。
	    重写方法一定不能抛出新的检査异常或者比被重写方法声明更加宽泛的检査型异常。例如，父类的一个方法声明了一个检査异常IOException，在重写这个方法时就不能抛出Exception，只能拋出IOException的子类异常，可以抛出非检査异常。

    注意：
	    重写的方法可以使用 @Override 注解来标识。
	    父类的成员方法只能被它的子类重写。
	    声明为 final 的方法不能被重写。
	    声明为 static 的方法不能被重写，但是能够再次声明。
	    构造方法不能被重写。
	    子类和父类在同一个包中时，子类可以重写父类的所有方法，除了声明为 private 和 final 的方法。
	    子类和父类不在同一个包中时，子类只能重写父类的声明为 public 和 protected 的非 final 方法。
	    如果不能继承一个方法，则不能重写这个方法。

多态性：
	继承、重写和向上转型是实现多态的三个必要条件。

	对面向对象来说，多态分为编译时多态和运行时多态。其中编译时多态是静态的，主要是指方法的重载，它是根据参数列表的不同来区分不同的方法。通过编译之后会变成两个不同的方法，在运行时谈不上多态。而运行时多态是动态的，它是通过动态绑定来实现的，也就是大家通常所说的多态性。

抽象类：
	abstract 关键字只能用于普通方法，不能用于 static 方法或者构造方法。

	使用 abstract 关键字修饰抽象方法时不能使用 private 修饰，因为抽象方法必须被子类重写。

	抽象类的定义和使用规则：
	    抽象类和抽象方法都要使用 abstract 关键字声明。
	    如果一个方法被声明为抽象的，那么这个类也必须声明为抽象的。而一个抽象类中，可以有 0~n 个抽象方法，以及 0~n 个具体方法。
	    抽象类不能实例化，也就是不能使用 new 关键字创建对象。

    抽象方法的 3 个特征：
	    抽象方法没有方法体。
	    抽象方法必须存在于抽象类中。
	    子类重写父类时，必须重写父类所有的抽象方法。

接口：
	接口的成员没有执行体，是由全局常量和公共的抽象方法所组成。 

	一个接口不能够实现另一个接口，但它可以继承多个其他接口。子接口可以对父接口的方法和常量进行重写。一个类可以继承一个父类，并同时实现多个接口，implements 部分必须放在 extends 部分之后。

	一个类实现了一个或多个接口之后，这个类必须完全实现这些接口里所定义的全部抽象方法（也就是重写这些抽象方法）；否则，该类将保留从父接口那里继承到的抽象方法，该类也必须定义成抽象类。

	特征：
		具有 public 访问控制符的接口，允许任何类使用；没有指定 public 的接口，其访问将局限于所属的包。
		方法的声明不需要其他修饰符，在接口中声明的方法，将隐式地声明为公有的（public）和抽象的（abstract）。
		在 java 接口中声明的变量其实都是常量，接口中的变量声明，将隐式地声明为 public、static 和 final，即常量，所以接口中定义的变量必须初始化。
		接口没有构造方法，不能被实例化。

内部类：
    内部类仍然是一个独立的类，在编译之后内部类会被编译成独立的.class文件，但是前面冠以外部类的类名和$符号。

    内部类不能用普通的方式访问。内部类是外部类的一个成员，因此内部类可以自由地访问外部类的成员变量，无论是否为 private 的。

    内部类声明成静态的，就不能随便访问外部类的成员变量，仍然是只能访问外部类的静态成员变量。

    内部类与外部类不能重名。

	成员内部类：
		实例内部类：
			实例内部类是指没有用 static 修饰的内部类，有的地方也称为非静态内部类。

				在外部类的静态方法和外部类以外的其他类中，必须通过外部类的实例创建内部类的实例。
				如果有多层嵌套，则内部类可以访问所有外部类的成员。
				在实例内部类中不能定义 static 成员，除非同时使用 final 和 static 修饰。

		静态内部类：
			静态内部类是指使用 static 修饰的内部类。

				在创建静态内部类的实例时，不需要创建外部类的实例。
				静态内部类中可以定义静态成员和实例成员。外部类以外的其他类需要通过完整的类名访问静态内部类中的静态成员，如果要访问静态内部类中的实例成员，则需要通过静态内部类的实例。 
				静态内部类可以直接访问外部类的静态成员，如果要访问外部类的实例成员，则需要通过外部类的实例去访问。

	局部内部类：
		局部内部类是指在一个方法中定义的内部类。

			局部内部类与局部变量一样，不能使用访问控制修饰符（public、private 和 protected）和 static 修饰符修饰。
			局部内部类只在当前方法中有效。 
			局部内部类中不能定义 static 成员。
			局部内部类中还可以包含内部类，但是这些内部类也不能使用访问控制修饰符（public、private 和 protected）和 static 修饰符修饰。
			在局部内部类中可以访问外部类的所有成员。
			在局部内部类中只可以访问当前方法中 final 类型的参数与变量。如果方法中的成员与外部类中的成员同名，则可以使用 <OuterClassName>.this.<MemberName> 的形式访问外部类中的成员。 

	使用内部类实现多重继承：
		java 提供的两种方法让我们实现多重继承：接口和内部类。

		内部类可以继承一个与外部类无关的类，即保证了内部类的独立性，也使多继承得以实现（一般是使用多个内部类继承多个父类，达到多继承效果）。

匿名类和匿名内部类：
	匿名类是指没有类名的内部类，必须在创建时使用 new 语句来声明类。

	匿名类的 new 语句声明一个新的匿名类，同时也可以对一个给定的类进行扩展，或者实现一个给定的接口。

	匿名类就是没有明确的给出名字的类，是类的一种简写形式。一般匿名对象只使用一次，而且匿名对象只在堆内存中开辟空间，而不存在栈内存的引用。即与 类名 对象名=new 类名（）形式相比较，单纯的 new 类名（）形式就是匿名对象，可以作为实际参数传递。

	匿名类实现方式：(实现方式是使用父类的构造方法或接口名)
	    继承一个类，重写其方法。
	    实现一个接口（可以是多个），实现其方法。
	    直接新建一个匿名类。

    特点：
    	匿名类和局部内部类一样，可以访问外部类的所有成员。如果匿名类位于一个方法中，则匿名类只能访问方法中 final 类型的局部变量和参数。
    	匿名类中允许使用非静态代码块进行成员初始化操作。
    	匿名类的非静态代码块会在父类的构造方法之后被执行。

	匿名内部类是局部内部类的一种匿名类形式，匿名类与匿名内部类的形式是：
		new A(){};//结尾的分号是必须的，代表了创建表达式的结束，而不是代表内部类的结束。

effectively final（java8+）：
	java 中局部内部类和匿名内部类访问的局部变量必须由 final 修饰，以保证内部类和外部类的数据一致性。但从 java 8 开始，我们可以不加 final 修饰符，由系统默认添加，当然这在 java 8 以前的版本是不允许的。java 将这个功能称为 effectively final 功能。

	一个非 final 的局部变量或方法参数，其值在初始化后就从未更改，那么该变量就是 effectively final。

	总的来说，规则没有改变，lambda表达式和匿名内部类访问的局部变量必须是 final 的，只是不需要程序员显式的声明变量为 final 的，从而节省时间。

lambda表达式（java8+）：
	lambda表达式（lambda expression）是一个匿名函数,也可称为闭包（Closure）。

	lambda表达式一种常见的用途就是作为参数传递给方法，这需要声明参数的类型声明为函数式接口类型（Calculable calc）。

	lambda表达式可以访问所在外层作用域定义的变量，包括成员变量和局部变量。
		成员变量包括实例成员变量和静态成员变量。在 lambda表达式中可以访问这些成员变量，此时的 lambda表达式与普通方法一样，对静态变量和成员变量可读可写。
		访问局部变量时，变量必须是 final 类型的（不可改变）,只能访问局部变量而不能进行修改。


	语法形式：
		(参数列表) -> { // lambda表达式体 }
			->被称为箭头操作符或 lambda 操作符，箭头操作符将 lambda表达式拆分成两部分：
			    左侧：lambda表达式的参数列表。
			    右侧：lambda表达式中所需执行的功能，用{ }包起来，即 lambda 体。

    优缺点：
    	优点：
		    代码简洁，开发迅速
		    方便函数式编程
		    非常容易进行并行计算
		    java 引入 lambda，改善了集合操作（引入 Stream API）
		缺点：
		    代码可读性变差
		    在非并行计算中，很多计算未必有传统的 for 性能要高
		    不容易进行调试

    函数式接口：
    	lambda表达式实现的接口不是普通的接口，而是函数式接口。如果一个接口中，有且只有一个抽象的方法（Object 类中的方法不包括在内），那这个接口就可以被看做是函数式接口。

    	在接口之前使用 @functionalInterface 注解修饰，试图增加一个抽象方法时会发生编译错误。但可以添加默认方法和静态方法。同时即使不使用该注解，只要满足函数式接口的定义，这仍然是一个函数式接口，使用起来都一样。

    	lambda表达式是一个匿名方法代码，java 中的方法必须声明在类或接口中，即lambda表达式所实现的匿名方法是在函数式接口中声明的那个唯一的抽象方法。

	简写方式：
		省略参数类型：
			lambda表达式可以根据上下文环境推断出参数类型,所以可以省略参数的类型。
				(int a, int b) -> { 省略为 (a, b) -> {
		省略参数小括号：
			如果 lambda表达式中的参数只有一个，可以省略参数小括号。
				(int a) -> { 省略为 a -> {
		省略return和大括号：
			如果 lambda表达式体中只有一条语句，那么可以省略 return 和大括号。
				(int a) -> {return a * a;} 省略为 a -> a * a * a;

	方法引用（java8+）：
		方法引用可以理解为 lambda表达式的快捷写法，如果实现比较复杂，复用的地方比较多，相比lambda表达式应当使用方法引用。

		方法引用虽然没有直接使用 lambda表达式，但也与 lambda表达式有关，与函数式接口有关，被引用方法的参数列表和返回值类型，必须与函数式接口方法参数列表和方法返回值类型一致。

		java 8 之后增加了双冒号::运算符，该运算符用于“方法引用”，而不是调用方法。
			ObjectRef::methodName 
				其中，ObjectRef 是类名或者实例名，methodName 是相应的方法名（使用上是普通的类调用静态方法和实例调用实例方法）。

lambda表达式与匿名内部类的联系和区别：
	java lambda 表达式的一个重要用法是简化某些匿名内部类的写法，因此它可以部分取代匿名内部类的作用。

	相同：
	    lambda 表达式与匿名内部类一样，都可以直接访问 effectively final 的局部变量，以及外部类的成员变量（包括实例变量和类变量）。
	    lambda 表达式创建的对象与匿名内部类生成的对象一样，都可以直接调用从接口中继承的默认方法。
    区别：
	    匿名内部类可以为任意接口创建实例——不管接口包含多少个抽象方法，只要匿名内部类实现所有的抽象方法即可；但 Lambda 表达式只能为函数式接口创建实例。
	    匿名内部类可以为抽象类甚至普通类创建实例；但 Lambda 表达式只能为函数式接口创建实例。
	    匿名内部类实现的抽象方法的方法体允许调用接口中定义的默认方法；但 Lambda 表达式的代码块不允许调用接口中定义的默认方法。


@@


@包装类

基本数据类型转换为包装类的过程称为装箱，包装类变为基本数据类型的过程称为拆箱。

手动实例化一个包装类称为手动拆箱装箱。java 1.5 版本之前必须手动拆箱装箱，之后可以自动拆箱装箱，也就是在进行基本数据类型和对应的包装类转换时，系统将自动进行装箱及拆箱操作，不用在进行手工操作。

常见的应用场景：
	int 和 Integer 的相互转换：
	 	int m = 500;
        Integer obj = new Integer(m);  // 手动装箱
        int n = obj.intValue();  // 手动拆箱
        Integer obj1 = new Integer(500);// 手动装箱
        obj.equals(obj1);//返回值为true
    String转换为int：
	    Integer.parseInt(str)
	    Integer.valueOf(str).intValue()
    int转换为String：
	    String s = String.valueOf(i);
	    String s = Integer.toString(i);
	    String s = "" + i;

Object类：
	Object 是 java 类库中的一个特殊类，也是所有类的父类。也就是说，java 允许把任何类型的对象赋给 Object 类型的变量。当一个类被定义后，如果没有指定继承的父类，那么默认父类就是 Object 类。

	Object 类是所有对象的父类，所有的对象都可以向 Object 进行转换，在这其中也包含了数组和接口类型，即一切的引用数据类型都可以使用 Object 进行接收。

	接口不能继承一个类，但是依然是 Object 类的子类，因为接口本身是引用数据类型，所以也可以进行向上转型操作。

	因为 Object 类可以接收任意的引用数据类型，所以在很多的类库设计上都采用 Object 作为方法的参数，这样操作起来会比较方便。

	由于 java 所有的类都是 Object 类的子类，所以任何 java 对象都可以调用 Object 类的方法。常见的方法有：
		Object clone() 	          创建与该对象的类相同的新对象
		boolean equals(Object) 	  比较两对象是否相等
		void finalize() 	      当垃圾回收器确定不存在对该对象的更多引用时，对象垃圾回收器调用该方法
		Class getClass() 	      返回一个对象运行时的实例类
		int hashCode() 	          返回该对象的散列码值
		void notify() 	          激活等待在该对象的监视器上的一个线程
		void notifyAll() 	      激活等待在该对象的监视器上的全部线程
		String toString() 	      返回该对象的字符串表示
		void wait() 	          在其他线程调用此对象的 notify() 方法或 notifyAll() 方法前，导致当前线程等待

		其中，toString()、equals() 方法和 getClass() 方法比较常用。 

		对于 equals() ，== 用来比较两个对象在堆区存放的地址是否相同（引用变量是否指向同一个实例），equals() 方法是比较两个对象的内容是否相等，通常字符串的比较只是关心内容是否相等。

		对于 toString() ，对象输出时一定会调用 Object 类中的 toString() 方法打印内容,可以重写 toString() 来获取对象的一些信息。

		对于 getClass() ，getClass() 方法返回对象所属的类，是一个 Class 对象，通过 Class 对象可以获取该类的各种信息，包括类名、父类以及它所实现接口的名字等。 
	        obj.getClass().getName();// 获取类名
	        obj.getClass().getSuperclass().getName();// 获取父类名
	        for (int i = 0; i < obj.getClass().getInterfaces().length; i++) { 
	        System.out.println(obj.getClass().getInterfaces()[i]);}// 获取实现的接口并输出

Number类：
	Number 是一个抽象类，也是一个超类（即父类）。Number 类属于 java.lang 包，所有的包装类（如 Double、float、Byte、Short、Integer 以及 long）都是抽象类 Number 的子类。

	Number 类定义了一些抽象方法，以各种不同数字格式返回对象的值。如 xxxValue() 方法，它将 Number 对象转换为 xxx 数据类型的值并返回。

System类：
	 java.lang.System；
	 	代表当前 java 程序的运行平台，系统级的很多属性和控制方法都放置在该类的内部。由于该类的构造方法是 private 的，所以无法创建该类的对象，也就是无法实例化该类。

	 System 类提供了一些类变量和类方法，允许直接通过 System 类来调用这些类变量和类方法。 

Integer类：
	构造方法：
	    Integer(int value)
	    Integer(String s)

	常用方法：
		byteValue() 	                    以 byte 类型返回该 Integer 的值
		shortValue() 	                    以 short 类型返回该 Integer 的值
		intValue() 	                        以 int 类型返回该 Integer 的值
		toString() 		                    返回一个表示该 Integer 值的 String 对象
		equals(Object obj) 	                比较此对象与指定对象是否相等
		compareTo(Integeranotherlnteger) 	在数字上比较两个 Integer 对象，相等则返回 0，小于参数值则返回负值，大于参数值则返回正值
		valueOf(String s) 	                返回保存指定的 String 值的 Integer 对象	
		parseInt(String s) 	                将数字字符串转换为 int 数值	

	常用常量：
	    MAX_VAlUE：值为 231-1 的常量，它表示 int 类型能够表示的最大值。
	    MIN_VAlUE：值为 -231 的常量，它表示 int 类型能够表示的最小值。
	    SIZE：用来以二进制补码形式表示 int 值的比特位数。
	    TYPE：表示基本类型 int 的 Class 实例。

float类：
	构造方法：
	    float(double value)
	    float(float value)
	    float(String s)

	常用方法：
		byteValue() 	         以 byte 类型返回该 float 的值
		doubleValue() 	         以 double 类型返回该 float 的值
		floatValue() 	         以 float 类型返回该 float 的值
		intValue() 	             以 int 类型返回该 float 的值（强制转换为 int 类型）
		longValue() 	         以 long 类型返回该 float 的值（强制转换为 long 类型）
		shortValue() 	         以 short 类型返回该 float 的值（强制转换为 short 类型）
		isNaN() 	             如果此 float 值是一个非数字值，则返回 true，否则返回 false
		isNaN(float v) 	         如果指定的参数是一个非数字值，则返回 true，否则返回 false
		toString() 	             返回一个表示该 float 值的 String 对象
		valueOf(String s) 	     返回保存指定的 String 值的 float 对象	
		parsefloat(String s) 	 将数字字符串转换为 float 数值

	常用常量：	
	    MAX_VAlUE：值为 1.4E38 的常量，它表示 float 类型能够表示的最大值。
	    MIN_VAlUE：值为 3.4E-45 的常量，它表示 float 类型能够表示的最小值。
	    MAX_EXPONENT:有限 float 变量可能具有的最大指数。
	    MIN_EXPONENT：标准化 float 变量可能具有的最小指数。
	    MIN_NORMAl：保存 float 类型数值的最小标准值的常量，即 2（-126）上标。
	    NaN：保存 float 类型的非数字值的常量。
	    SIZE：用来以二进制补码形式表示 float 值的比特位数。
	    TYPE：表示基本类型 float 的 Class 实例。

Double类：
	构造方法：
		Double(double value)
		Double(String s)

	常用方法：
		byteValue() 			以 byte 类型返回该 Double 的值
		doubleValue() 			以 double 类型返回该 Double 的值
		fioatValue() 			以 float 类型返回该 Double 的值
		intValue() 				以 int 类型返回该 Double 的值（强制转换为 int 类型）
		longValue() 			以 long 类型返回该 Double 的值（强制转换为 long 类型）
		shortValue() 			以 short 类型返回该 Double 的值（强制转换为 short 类型）
		isNaN() 				如果此 Double 值是一个非数字值，则返回 true，否则返回 false
		isNaN(double v) 		如果指定的参数是一个非数字值，则返回 true，否则返回 false
		toString() 				返回一个表示该 Double 值的 String 对象
		valueOf(String s) 		返回保存指定的 String 值的 Double 对象
		parseDouble(String s) 	将数字字符串转换为 Double 数值

	常用常量：
	    MAX_VAlUE:值为 1.8E308 的常量，它表示 double 类型的最大正有限值的常量。
	    MIN_VAlUE：值为 4.9E-324 的常量，它表示 double 类型数据能够保持的最小正非零值的常量。
	    NaN：保存 double 类型的非数字值的常量。
	    NEGATIVE_INfINITY：保持 double 类型的负无穷大的常量。
	    POSITIVE_INfINITY：保持 double 类型的正无穷大的常量。
	    SIZE：用秦以二进制补码形式表示 double 值的比特位数。
	    TYPE：表示基本类型 double 的 Class 实例。

Character类：
	构造方法：
		Character(char c)

	常用方法：
		void Character(char value) 					构造一个新分配的 Character 对象，用以表示指定的 char 值
		char charValue() 							返回此 Character 对象的值，此对象表示基本 char 值
		int compareTo(Character anotherCharacter) 	根据数字比较两个 Character 对象，返回一个int值，这个值是两个字符比较后的标准代码差值
		boolean equals(Character anotherCharacter) 	将此对象与指定对象比较，当且仅当参数不是 null，而 是一个与此对象包含相同 char 值的 Character 对象时， 结果才是 true
		boolean isDigit(char ch) 					确定指定字符是否为数字，如果通过 Character. getType(ch) 提供的字符的常规类别类型为 DECIMAl_DIGIT_NUMBER，则字符为数字
		boolean isletter(int codePoint) 			确定指定字符（Unicode 代码点）是否为字母
		boolean isletterOrDigit(int codePoint) 		确定指定字符（Unicode 代码点）是否为字母或数字
		boolean islowerCase(char ch) 				确定指定字符是否为小写字母
		boolean isUpperCase(char ch) 				确定指定字符是否为大写字母
		char tolowerCase(char ch) 					使用来自 UnicodeData 文件的大小写映射信息将字符参数转换为小写
		char toUpperCase(char ch) 					使用来自 UnicodeData 文件的大小写映射信息将字符参数转换为大写

Boolean类：
	构造方法：
		Boolean(boolean boolValue)
    	Boolean(String boolString) boolString 包含字符串 true（不区分大小写），那么新的 Boolean 对象将包含 true，否则将包含 false

    常用方法：
		booleanValue() 			将 Boolean 对象的值以对应的 boolean 值返回	
		equals(Object obj) 		判断调用该方法的对象与 obj 是否相等。当且仅当参数不是 null，且与调用该方法的对象一样都表示同一个 boolean 值的 Boolean 对象时，才返回 true
		parseBoolean(String s) 	将字符串参数解析为 boolean 值
		toString() 				返回表示该 boolean 值的 String 对象
		valueOf(String s) 		返回一个用指定的字符串表示的 boolean 值 	

	常用常量：
	    TRUE：对应基值 true 的 Boolean 对象。
	    fAlSE：对应基值 false 的 Boolean 对象。
	    TYPE：表示基本类型 boolean 的 Class 对象。

Byte类：
	构造方法：
		Byte(byte value)
		Byte(String s) 必须使用数值型的 String 变量作为参数才能创建成功，否则会抛出 NumberformatException 异常

	常用方法：
		byteValue() 			以一个 byte 值返回 Byte 对象
		compareTo(Byte bytel) 	在数字上比较两个 Byte 对象
		doubleValue() 			以一个 double 值返回此 Byte 的值
		intValue() 				以一个 int 值返回此 Byte 的值	
		parseByte(String s) 	将 String 型参数解析成等价的 byte 形式
		toStringO 				返回表示此 byte 值的 String 对象
		valueOf(String s) 		返回一个保持指定 String 所给出的值的 Byte 对象	
		equals(Object obj) 		将此对象与指定对象比较，如果调用该方法的对象与 obj 相等 则返回 true，否则返回 false	

	常用常量：
	    MIN_VAlUE：byte 类可取的最小值。
	    MAX_VAlUE：byte 类可取的最大值。
	    SIZE：用于以二进制补码形式表示的 byte 值的位数。
	    TYPE：表示基本类 byte 的 Class 实例。


@@


@String字符串类及字符串处理

String类是final类，也即意味着String类不能被继承，并且它的成员方法都默认为final方法。在java中，被final修饰的类是不允许被继承的，并且该类中的成员方法都默认为final方法。对String对象的任何改变都不影响到原对象，相关的任何change操作都会生成新的对象。jVM为了减少字符串对象的重复创建，其维护了一个特殊的内存，这段内存被称为字符串常量池或者字符串字面量池。字符串常量池实现的前提条件就是java中String对象是不可变的，这样可以安全保证多个变量共享同一个对象。如果java中的String对象可变的话，一个引用操作改变了对象的值，那么其他的变量也会受到影响，显然这样是不合理的。当代码中出现字面量形式创建字符串对象时，jVM首先会对这个字面量进行检查，如果字符串常量池中存在相同内容的字符串对象的引用，则将这个引用返回，否则新的字符串对象被创建，然后将这个引用放入字符串常量池，并返回该引用。

"测试字符串" 形式是常量， String s1=new String（"测试字符串"） 形式是一个对象 s1 和一个常量 "测试字符串" ，String s1="测试字符串" String s2="测试字符串" 形式是两个对象 s1 s2 和一个常量 "测试字符串" ，并且s1和s2具有相同的实体。 "测试字符串" 在字符串常量池中（编译期），s1，s2在堆中（运行期）。
	
String s="a"+"b"+"c" 语句中，“a”,"b", "c"都是常量，编译时就直接存储他们的字面值，而不是他们的引用，在编译时就直接将它们连接的结果提取出来变成"abc"了，即 "a"+"b"+"c"=="abc" 。

字符串的连接字符 + ，任何和字符串连接的操作数都会被转换成字符串形式，并且最终生成的是一个String对象。

String类的底层是通过char数组来保存字符串的，它的length（）返回数组大小，而一个汉字用一个char表示。
	
字符串长度：
	字符串名.length()

字符串大小写转换：
	字符串名.toLowerCase()    // 将字符串中的字母全部转换为小写，非字母不受影响
	字符串名.toUpperCase()    // 将字符串中的字母全部转换为大写，非字母不受影响

字符串去除空格：
	字符串名.trim()
		字符串中的每个空格占一个位置，如果不确定要操作的字符串首尾是否有空格，最好在操作之前调用该字符串的 trim() 方法去除首尾空格，然后再对其进行操作。

	trim() 只能去掉字符串中前后的半角空格（英文空格），而无法去掉全角空格（中文空格）。
		str = str.replace((char) 12288, ' ')  // 将中文空格替换为英文空格，其中，12288 是中文全角空格的 unicode 编码。

字符串截取：
	substring(int beginIndex) 
		//此方式用于提取从索引位置开始至结尾处的字符串部分。调用时，括号中是需要提取字符串的开始位置，方法的返回值是提取的字符串。
	substring(int beginIndex，int endIndex)  
		//此方法中的 beginIndex 表示截取的起始索引，截取的字符串中包括起始索引对应的字符；endIndex 表示结束索引，截取的字符串中不包括结束索引对应的字符，如果不指定 endIndex，则表示截取到目标字符串末尾。该方法用于提取位置 beginIndex 和位置 endIndex 位置之间的字符串部分。

	substring() 方法是按字符截取，而不是按字节截取。

	对于开始位置 beginIndex， java 是基于字符串的首字符索引为 0 处理的，但是对于结束位置 endIndex，java 是基于字符串的首字符索引为 1 来处理的。

字符串分割：
	split() 方法可以按指定的分割符对目标字符串进行分割，分割后的内容存放在字符串数组中:
	    str.split(String sign)
	    str.split(String sign,int limit)
			str 为需要分割的目标字符串。
		    sign 为指定的分割符，可以是任意字符串。
		    limit 表示分割后生成的字符串的限制个数，如果不指定，则表示不限制，直到将整个目标字符串完全分割为止。  

    注意：
    	“.”和“|”都是转义字符，必须得加“\\”。
	    	如果用“.”作为分隔的话，必须写成String.split("\\.")，这样才能正确的分隔开，不能用String.split(".")。
	    	如果用“|”作为分隔的话，必须写成String.split("\\|")，这样才能正确的分隔开，不能用String.split("|")。
    	如果在一个字符串中有多个分隔符，可以用“|”作为连字符，比如：“acount=? and uu =? or n=?”，把三个都分隔出来，可以用String.split("and|or")。
  
字符串的替换：
	字符串.replace(String oldChar, String newChar)  
		//replace() 方法用于将目标字符串中的指定字符（串）替换成新的字符（串）。其中，oldChar 表示被替换的字符串，newChar 表示用于替换的字符串。replace() 方法会将字符串中所有 oldChar 替换成 newChar。
	字符串.replacefirst(String regex, String replacement)
		//replacefirst() 方法用于将目标字符串中匹配某正则表达式的第一个子字符串替换成新的字符串。其中，regex 表示正则表达式；replacement 表示用于替换的字符串。
	字符串.replaceAll(String regex, String replacement)
		//replaceAll() 方法用于将目标字符串中匹配某正则表达式的所有子字符串替换成新的字符串。其中，regex 表示正则表达式，replacement 表示用于替换的字符串。

字符串比较：
	str1.equals(str2)  
		//区分大小写。特指String字符串中方法。
	str1.equalsIgnoreCase()  
		//不区分大小写。
	str.compareTo(String otherstr)  
		//按字典顺序比较两个字符串的大小，该比较是基于字符串各个字符的 Unicode 值。如果按字典顺序 str 位于 otherster 参数之前，比较结果为一个负整数；如果 str 位于 otherstr 之后，比较结果为一个正整数；如果两个字符串相等，则结果为 0。

	如果两个字符串调用 equals() 方法返回 true，那么调用 compareTo() 方法会返回 0。 

空字符串和null：
	new String()和“”是一个长度为 0 且占内存的空字符串，在内存中分配一个空间，可以使用 Object 对象中的方法。
	null 是空引用，表示一个对象的值，没有分配内存，调用 null 的字符串的方法会抛出空指针异常。
	String 变量可以存放一个特殊的值 null，这表示目前没有任何对象与该变量关联。

	if (str.length() == 0)
	if (str.equals(""))
	if (str == null)

	if (str != null && str.length() != 0)  //首先要检查 str 不为 null。如果在一个 null 值上调用方法，会出现错误。

字符串查找：
    str.indexOf(value)
    str.indexOf(value,int fromIndex)
    	//indexOf() 方法用于返回字符（串）在指定字符串中首次出现的索引位置，如果能找到，则返回索引值，否则返回 -1。其中，str 表示指定字符串；value 表示待查找的字符（串）；fromIndex 表示查找时的起始索引，如果不指定 fromIndex，则默认从指定字符串中的开始位置（即 fromIndex 默认为 0）开始查找。

    str.lastIndexOf(value)
    str.lastlndexOf(value, int fromIndex)
    	//lastIndexOf() 方法用于返回字符（串）在指定字符串中最后一次出现的索引位置，如果能找到则返回索引值，否则返回 -1。lastIndexOf() 方法的查找策略是从右往左查找，如果不指定起始索引，则默认从字符串的末尾开始查找。

	字符串名.charAt(索引值)
		//字符串本质上是字符数组，因此它也有索引，索引从零开始。

StringBuffer类：
	StringBuffer 类可以比 String 类更高效地处理字符串。因为 StringBuffer 类是可变字符串类，创建 StringBuffer 类的对象后可以随意修改字符串的内容。每个 StringBuffer 类的对象都能够存储指定容量的字符串，如果字符串的长度超过了 StringBuffer 类对象的容量，则该对象的容量会自动扩大。

	构造方法：
	    StringBuffer() //构造一个空的字符串缓冲区，并且初始化为 16 个字符的容量。
	    StringBuffer(int length) //创建一个空的字符串缓冲区，并且初始化为指定长度 length 的容量。
	    StringBuffer(String str) //创建一个字符串缓冲区，并将其内容初始化为指定的字符串内容 str，字符串缓冲区的初始容量为 16 加上字符串 str 的长度。

    StringBuffer 对象.append(String str) //StringBuffer 类的 append() 方法用于向原有 StringBuffer 对象中追加内容到当前 StringBuffer 对象的末尾。

    StringBuffer 对象.setCharAt(int index, char ch) //StringBuffer 类的 setCharAt() 方法用于在字符串的指定索引位置替换一个字符。

    StringBuffer 对象.reverse() //StringBuffer 类中的 reverse() 方法用于将字符串序列用其反转的形式取代。

    StringBuffer 对象.deleteCharAt(int index) 
    	//deleteCharAt() 方法用于移除序列中指定位置的字符。
    StringBuffer 对象.delete(int start,int end) 
    	//delete() 方法用于移除序列中子字符串的字符，删除指定区域以内的所有字符，start 表示要删除字符的起始索引值（包括索引值所对应的字符），end 表示要删除字符串的结束索引值（不包括索引值所对应的字符）。

String、StringBuffer和StringBuilder类的区别：
	可变字符串类 StringBuffer 和 StringBuilder （译名 字符串缓冲区）。

	（String） implements （CharSequence）； //是final class，一般情况下速度最慢。
	（StringBuilder，StringBuffer） extends （AbstractStringBuilder implements CharSequence,Appendable）; //StringBuffer线程安全但速度相对较慢，StringBuilder线程不安全但速度相对较快，两者都是可变字符串类。

	适用：
		操作少量的数据使用 String。
		单线程操作大量数据使用 StringBuilder。
		多线程操作大量数据使用 StringBuffer。

正则表达式（概述，非详细）：
	正则表达式（Regular Expression）又称正规表示法、常规表示法，在代码中常简写为 regex、regexp 或 RE，它是计算机科学的一个概念。由普通的字符（如字符 a~z）以及特殊字符（元字符）组成的文字模式，它用以描述在查找文字主体时待匹配的一个或多个字符串。	

	String类中关于正则表达式的方法：
	    boolean matches(String regex)：判断该字符串是否匹配指定的正则表达式。
	    String replaceAll(String regex, String replacement)：将该字符串中所有匹配 regex 的子串替换成 replacement。
	    String replacefirst(String regex, String replacement)：将该字符串中第一个匹配 regex 的子串替换成 replacement。
	    String[] split(String regex)：以 regex 作为分隔符，把该字符串分割成多个子串。

	Pattern类和Matcher类：
		java.util.regex 是一个用正则表达式所订制的模式来对字符串进行匹配工作的类库包。它包括两个类：Pattern 和 Matcher。


@@


@数组

特征：
	一致性：数组只能保存相同数据类型元素，元素的数据类型可以是任何相同的数据类型。
    有序性：数组中的元素是有序的，通过下标访问。
    不可变性：数组一旦初始化，则长度（数组中元素的个数）不可变。

数组元素可以是任何类型，包括数组类型。

数组类型是从抽象基类 Array 派生的引用类型。

数组可以是一维数组、二维数组或多维数组。

当指定的下标值超出数组的总长度时，会拋出 ArraylndexOutOfBoundsException 异常。

java数组也是一种数据类型，数组整体属于引用数据类型，当声明一个数组变量时，其实是创建了一个类型为“数据类型[]”（如 int[]、double[]、String[]）的数组对象。

阶段：
	声明：
		type[] arrayName;    // 数据类型[] 数组名;推荐使用，比较直观。下面会默认使用此格式和其衍生。
		type arrayName[];    // 数据类型 数组名[];不推荐使用，格式被支持，但不规范。

		声明了数组，只是得到了一个存放数组的变量，并没有为数组元素分配内存空间，不能使用。

	分配空间：
		在 java 中可以使用 new 关键字来给数组分配空间。

		在声明数组时就给它分配空间：
			type[] arrayName = new type[size];    // 数据类型[] 数组名 = new 数据类型[数组长度];

		使用 new 指定数组元素的值：
			type[] arrayName = new type[]{值 1,值 2,值 3,值 4,• • •,值 n};

			不要在进行数组初始化时，既指定数组的长度，也为每个数组元素分配初始值，这样会造成代码错误。

		直接指定数组元素的值:
			type[] arrayName = {值 1,值 2,值 3,...,值 n};//不可以分开使用，例如arrayName = {值 1,值 2,值 3,...,值 n}是错误的。

		一旦声明了数组的大小，就不能再修改。分配空间时数组的长度是必需的，不能缺少。

		数组只分配空间，其中的数组元素是有初值的。

二维数组：
	以第一个下标表示元素所在的行，第二个下标表示元素所在的列。

	在 java 中二维数组被看作数组的数组，即二维数组为一个特殊的一维数组，其每个元素又是一个一维数组。

	在二维数组中，直接使用 length 属性获取的是数组的行数，在指定的索引后加上 length（如 array[0].length）表示的是该行拥有多少个元素，即列数。

	声明：
		type[][] arrayName;    // 数据类型[][] 数组名;type 表示二维数组的类型，arrayName 表示数组名称，第一个中括号表示行，第二个中括号表示列。

	分配空间：
		type[][] arrayName = new type[][]{值 1,值 2,值 3,…,值 n};    // 在定义时初始化，eg：int[][] temp = new int[][]{{1,2},{3,4}};
		type[][] arrayName = new type[size1][size2];    // 给定空间，在赋值
		type[][] arrayName = new type[size][];    // 数组第二维长度为空，可变化

多维数组：
	参考二维数组的衍生。

	二维数组是一维数组，其数组元素是一维数组。三维数组也是一维数组，其数组元素是二维数组……

不规则数组：
	低维数组包含的元素个数不相同的高维数组。

	先初始化高维数组，然后再分别逐个初始化低维数组。因为每个低维数组的元素个数是不同的，与规则高维数组包含的个数是不同的。


@@


@数字处理和日期类

Math类：
	在 java 中 Math 类封装了常用的数学运算，提供了基本的数学操作，如指数、对数、平方根和三角函数等。Math 类位于 java.lang 包，它的构造方法是 private 的，因此无法创建 Math 类的对象，并且 Math 类中的所有方法都是类方法，可以直接通过类名来调用它们。

	Math 类中包含 E 和 PI 两个静态常量，正如它们名字所暗示的，它们的值分别等于 e（自然对数）和 π（圆周率）。 

生成随机数（random()和Random类）：
	Math 类的 random() 方法和Random 类。

	Random 类提供了丰富的随机数生成方法，可以产生 boolean、int、long、float、byte 数组以及 double 类型的随机数，这是它与 random() 方法最大的不同之处。random() 方法只能产生 double 类型的 0~1 的随机数。

	Random 类位于 java.util 包中，该类常用的有如下两个构造方法。
	    Random()：该构造方法使用一个和当前系统时间对应的数字作为种子数，然后使用这个种子数构造 Random 对象。
	    Random(long seed)：使用单个 long 类型的参数创建一个新的随机数生成器。

	    Random 类提供的所有方法生成的随机数字都是均匀分布的，也就是说区间内部的数字生成的概率是均等的。

数字格式化：
	DecimalFormat 是 NumberFormat 的一个子类，用于格式化十进制数字。

	使用（eg）：
		 DecimalFormat df1 = new DecimalFormat("0.0");
		 float f =5487.45697f;
		 System.out.println("0.0 格式：" + df1.format(f));

		 0.0 格式：5487.5

大数字运算（BigInteger类和BigDecimal类）：
	java.math.BigInteger 类和 java.math.BigDecimal 类，这两个类用于高精度计算，其中 BigInteger 类是针对整型大数字的处理类，而 BigDecimal 类是针对大小数的处理类。

	BigInteger 支持任意精度的整数，也就是说在运算中 BigInteger 类型可以准确地表示任何大小的整数值。
	BigDecimal 类支持任何精度的浮点数，可以用来精确计算货币值。

时间日期的处理（java Date类、Calendar类）：
	Date 类主要封装了系统的日期和时间的信息，Calendar 类则会根据系统的日历来解释 Date 对象。

	Date类：
		Date 类表示系统特定的时间戳，可以精确到毫秒。Date 对象表示时间的默认顺序是星期、月、日、小时、分、秒、年。

		构造方法：
		    Date()：此种形式表示分配 Date 对象并初始化此对象，以表示分配它的时间（精确到毫秒），使用该构造方法创建的对象可以获取本地的当前时间。
		    Date(long date)：此种形式表示从 GMT 时间（格林尼治时间）1970 年 1 月 1 日 0 时 0 分 0 秒开始经过参数 date 指定的毫秒数。

		    Date 类的无参数构造方法获取的是系统当前的时间，显示的顺序为星期、月、日、小时、分、秒、年。

		    Date 类带 long 类型参数的构造方法获取的是距离 GMT 指定毫秒数的时间，60000 毫秒是一分钟，而 GMT（格林尼治标准时间）与 CST（中央标准时间）相差 8 小时，也就是说 1970 年 1 月 1 日 00:00:00 GMT 与 1970 年 1 月 1 日 08:00:00 CST 表示的是同一时间。 因此距离 1970 年 1 月 1 日 00:00:00 CST 一分钟的时间为 1970 年 1 月 1 日 00:01:00 CST，即使用 Date 对象表示为 Thu jan 01 08:01:00 CST 1970。

    Calendar类：
    	Calendar 类是一个抽象类，它为特定瞬间与 YEAR、MONTH、DAY_OF—MONTH、HOUR 等日历字段之间的转换提供了一些方法，并为操作日历字段（如获得下星期的日期） 提供了一些方法。

    	创建 Calendar 对象不能使用 new 关键字，因为 Calendar 类是一个抽象类，但是它提供了一个 getInstance() 方法来获得 Calendar类的对象。getInstance() 方法返回一个 Calendar 对象，其日历字段已由当前日期和时间初始化。 
		    Calendar c = Calendar.getInstance();
		    	当创建了一个 Calendar 对象后，就可以通过 Calendar 对象中的一些方法来处理日期、时间。


@@


@异常处理

异常：
	java异常（exception）又称为例外，中断正在执行程序的正常指令流。

	异常产生的原因主要有：
		java内部错误，java虚拟机发生异常。
		编写的程序代码中的错误产生的异常。
		通过throw语句手动生成的异常，一般用于告知该方法的调用者一些必要信息。

	抛出（throw）是指生成异常对象，并提交给运行时系统的过程。捕获（catch）是指运行时系统在方法的调用栈中查找，直到找到能处理该类型异常的对象的过程。

	java中使用异常类，java中所有异常类都是java.lang.throwable的子类。

	结构：
		Throwable是所有错误类与异常类的超类，下有两个子类Error（错误）和Exception（异常）。
			Error错误类定义了在通常情况下不希望被程序捕获的异常，这种错误是致命的，程序无法对其进行修复。
			Exception异常类用于用户程序可能出现异常情况，也是用来创建自定义异常的类。Exception下又分为运行时异常（不检查异常）和非运行时异常（检查异常）。
				运行时异常都是RuntimeException类及其子类异常，又称为不检查异常，程序可以选择是否进行捕获处理。运行时异常一般由程序逻辑错误引起，应该从逻辑解决避免发生。
				非运行时异常是指运行时异常以外的异常，属于Exception类及其子类，一般由语法角度的错误造成，不处理就无法通过编译。

	java中，只有继承了Throwable类的实例才能被throw或catch处理。

异常处理机制与基本结构：
	异常处理的五个关键字：
		try，catch用于捕获并处理异常，finally用于在一般情况下必须执行的语句，throw抛出异常，throws声明异常。

	通过try，catch捕获并处理异常，catch可以有多个，用以匹配多个异常。

	在方法的声明处通过throws声明处理不了的异常或要转型的异常，来由上层的调用方法处理。

try catch语句详解：
	try语句块中抛出异常并处理后，会跳过剩余try语句块内容，转至catch语句块后的第一条语句进行执行。

	try语句块没有抛出异常，catch语句块被跳过，从catch语句块后的第一条语句进行执行。

	try，catch语句块的{}不可省略，即使只有一条语句。

	try语句块中声明的变量是局部变量，只在try块内有效和可访问。

	异常信息输出方法：
		printStackTrace（）：指出异常的类型、性质栈层次及异常在代码中的位置。
		getMessage（）：输出异常的性质。
		toString（）：输出异常的类型与性质。

	当有多个catch块时，执行一个catch块后其它catch块会被跳过。

	catch块先捕获子类异常再捕获父类异常，子类异常要在父类异常之前，否则捕获不到，异常类型等被父类覆盖。

	catch匹配规则时异常对象是否为某个指定异常类类型或子类类型。

try catch finally语句：
	java的垃圾回收机制不会回收任何物理资源，垃圾回收机制只回收堆内存中对象所占用的内存。

	try代码块是必需的，没有try块，catch或finally不能存在，当存在try块时，catch与finally至少存在一个。

	catch位于try后，finally位于catch后。

	不使用catch块，异常抛出后得不到捕获和处理。

	try、catch、finally语句块的执行情况如下

	除非在 try 块、catch 块中调用了退出虚拟机的方法System.exit（int status），否则不管在 try 块或者 catch 块中执行怎样的代码，出现怎样的情况，异常处理的 finally 块总会全部执行。



finally和return的执行顺序：
	finally 代码块中的 return 语句一定会执行，即finally中的return会导致try与catch被跳过。

	当 try 代码块和 catch 代码块中有 return 语句时，finally 仍然会被执行。执行 try 代码块或 catch 代码块中的 return 语句之前，都会先执行 finally 语句。无论在 finally 代码块中是否修改返回值，返回值都不会改变，仍然是执行 finally 代码块之前的值（因为适配前一条，finally在try与catch之前执行）。

自动资源管理（java7+,java9+）：
	自动资源管理（Automatic Resource Management）是在 try 语句上的扩展，主要释放不再需要的文件或其他资源，能自动关闭文件。

	自动资源管理替代了 finally 代码块，并优化了代码结构和提高程序可读性。如果程序需要，自动关闭资源的 try 语句后也可以带多个 catch 块和一个 finally 块。

	java7+:
	    try (声明或初始化资源语句) {
	        // 可能会生成异常语句
	    } catch(Throwable e1){
	        // 处理异常e1
	    } catch(Throwable e2){
	        // 处理异常e1
	    } catch(Throwable eN){
	        // 处理异常eN
	    }
		    try 语句中声明的资源被隐式声明为 final，资源的作用局限于带资源的 try 语句。
		    可以在一条 try 语句中声明或初始化多个资源，每个资源以;隔开即可。
		    需要关闭的资源必须实现了 AutoCloseable 或 Closeable 接口。

		    Closeable 是 AutoCloseable 的子接口，Closeable 接口里的 close() 方法声明抛出了 IOException，因此它的实现类在实现 close() 方法时只能声明抛出 IOException 或其子类；AutoCloseable 接口里的 close() 方法声明抛出了 Exception，因此它的实现类在实现 close() 方法时可以声明抛出任何异常。

    java9+:
    	Java 9 再次增强了这种 try 语句。Java 9 不要求在 try 后的圆括号内声明并创建资源，只需要自动关闭的资源有 final 修饰或者是有效的 final (effectively final)，Java 9 允许将资源变量放在 try 后的圆括号内。

throws和throw：
	throws声明异常：
		returnType method_name(paramList) throws Exception 1,Exception2,…{…}；//returnType 表示返回值类型；method_name 表示方法名；paramList 表示参数列表；Exception 1，Exception2，… 表示异常类。
			如果有多个异常类，它们之间用逗号分隔。这些异常类可以是方法中调用了可能拋出异常的方法而产生的异常，也可以是方法体中生成并拋出的异常。

	使用 throws 声明抛出异常的思路是，当前方法不知道如何处理这种类型的异常，该异常应该由向上一级的调用者处理；如果 main 方法也不知道如何处理这种类型的异常，也可以使用 throws 声明抛出异常，该异常将交给 JVM 处理。JVM 对异常的处理方法是，打印异常的跟踪栈信息，并中止程序运行，这就是前面程序在遇到异常后自动结束的原因。

		子类方法声明抛出的异常类型应该是父类方法声明抛出的异常类型的子类或相同，子类方法声明抛出的异常不允许比父类方法声明抛出的异常多。

	throw抛出异常：
		throw ExceptionObject;//其中，ExceptionObject 必须是 Throwable 类或其子类的对象。如果是自定义异常类，也必须是 Throwable 的直接或间接子类。

	throws 通常不用显式地捕获异常，可由系统自动将所有捕获的异常信息抛给上级方法； throw 则需要用户自己捕获相关的异常，而后再对其进行相关包装，最后将包装后的异常信息抛出。

多异常捕获（java7+）：
	形式：
	    try{
	        // 可能会发生异常的语句
	    } catch (IOException | ParseException e) {
	        // 调用方法methodA处理
	    }
	    	捕获多种类型的异常时，异常变量有隐式的 final 修饰，因此程序不能对异常变量重新赋值。该 catch 块可以同时捕获多种类型的异常。

自定义异常：
	自定义异常需要继承Exception类或其子类，其中自定义运行时异常需要继承RuntimeException类或其子类。

	命名规则：
		一般命名为xxxException，xxx为异常的作用。

	构造方法：
		无参构造方法：
			public xxxException（）{super（）；}
		有参构造方法：
			public xxxException（String s）{super（s）；}//以字符串形式接收一个定制的异常信息，并传递给超类的构造方法。

		一般构造方法会同时拥有以上两种。

异常处理规则：
	不要过度使用异常。

	不要使用过于庞大的try块，应当把大块的 try 块分割成多个可能出现异常的程序段落，并把它们放在单独的 try 块中，从而分别捕获并处理异常。 

	避免使用 Catch All 语句。

	不要忽略捕获到的异常。


@@


@集合、泛型和枚举

java所有集合类都位于java.util包下，集合中只能保存对象（实际上保存的是对象的引用变量）。

结构：
	Collection extends Iterator;
	Queue,List,Set implements Collection;
	PriorityQueue,Dueue implements Queue;
	LinkedList,ArrayList,vector implements List;
	EnumSet,TreeSet,HashSet implements Set;
	ArrayDueue extends LinkedList implements Dueue;
	Stack extends Vector;
	JumboEnumSet,RegularEnumSet extends EnumSet;
	LinkedHashSet extends HashSet;
	HashMap,WeakHashMap,IdentityHashMap,HashTable,TreeMap,EnumMap implements Map;
	LinkeMap extends HashMap;
	Properties extends HashTable;

collection接口：
	常用方法：
		boolean add(E e) 					向集合中添加一个元素，如果集合对象被添加操作改变了，则返回 true。E 是元素的数据类型
		boolean addAll(Collection c) 		向集合中添加集合 c 中的所有元素，如果集合对象被添加操作改变了，则返回 true。
		void clear() 						清除集合中的所有元素，将集合长度变为 0。
		boolean contains(Object o) 			判断集合中是否存在指定元素
		boolean containsAll(Collection c) 	判断集合中是否包含集合 c 中的所有元素
		boolean isEmpty() 					判断集合是否为空
		Iterator<E>iterator() 				返回一个 Iterator 对象，用于遍历集合中的元素
		boolean remove(Object o) 			从集合中删除一个指定元素，当集合中包含了一个或多个元素 o 时，该方法只删除第一个符合条件的元素，该方法将返回 true。
		boolean removeAll(Collection c) 	从集合中删除所有在集合 c 中出现的元素（相当于把调用该方法的集合减去集合 c）。如果该操作改变了调用该方法的集合，则该方法返回 true。
		boolean retainAll(Collection c) 	从集合中删除集合 c 里不包含的元素（相当于把调用该方法的集合变成该集合和集合 c 的交集），如果该操作改变了调用该方法的集合，则该方法返回 true。
		int size() 							返回集合中元素的个数
		Object[] toArray() 					把集合转换为一个数组，所有的集合元素变成对应的数组元素。
			其他详见java API文档。

	正常情况下，集合中被放入的对象会被集合统一看作Object看待，即存入集合的对象不会保存对象的类型。

List集合：
	List集合是有顺序的，单元素的，元素可以重复，默认顺序为添加顺序，常用的实现类为ArrayList和LinkedList。

	ArrayList：
		提供了高效的的基于索引访问元素的方式，对尾部成员增加和删除速度较快，允许对元素进行快速随机访问，但是向非尾部成员位置插入与删除的速度较慢。

		构造方法：
			ArrayList（）；//构建一个默认拥有10个元素位置的空列表。
			ArrayList（Collection<? extends E> C）;//构建一个包含指定Collection类型元素的列表，这些元素的顺序是指定Collection类型的迭代器返回的元素的顺序。

	LinkedList
		是一种链表结构，对于向集合中插入和删除元素速度较快，但是随机访问的速度较慢（指检索集合中特定索引位置的元素）。

		常用方法：
			void addFirst(E e) 	将指定元素添加到此集合的开头
			void addLast(E e) 	将指定元素添加到此集合的末尾
			E getFirst() 		返回此集合的第一个元素
			E getLast() 		返回此集合的最后一个元素
			E removeFirst() 	删除此集合中的第一个元素
			E removeLast() 		删除此集合中的最后一个元素

	ArrayList和LinkedList之间的练习和区别：
		ArrayList是基于动态数组实现的，LinkedList是基于链表实现的。其中，ArrayList访问速度优于LinkedList，LinkedList占用空间较大，但批量插入或删除元素时比ArrayList速度快。

		一般来说，速度较快会导致占用空间变大，空间上的节省一般会造成速度变慢。

Set集合：
	Set集合中的元素是无序的，不可重复的，只能有一个null元素。

	HashSet：
		


@@


@反射机制

Java 反射机制在一般的 Java 应用开发中很少使用，即便是 Java EE 阶段也很少使用。但应当熟悉其流程、结构和原理，了解细节，因为大部分相关框架等使用了该机制。







@@


@输入/输出流

（待补）


@@


@java注解

（待补）


@@


@java待分类






@@


>>>>>
#




#Spring
>>>>>


@

$$


@@


>>>>>
#