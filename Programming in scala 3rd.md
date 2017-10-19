#Chapter 2 第二章

##First Steps in Scala  第一步

It's time to write some Scala code. Before we start on the in-depth Scala tutorial, we put in two chapters that will
 give the big picture of Scala, and most importantly, get you writing code. We encourage you to actually try out
 all the code examples presented in this chapter and the next as you go. The best way to start learning Scala is
 to program it.
 
 是时候写些Scala代码了。在我们深入介绍Scala之前，我们将用两章来整体介绍一下Scala，最重要的是，带你写代码。我们鼓励你亲自测试本章以及后续章节
 的代码示例。编码是学习Scala的最好方法。
 
 To run the examples in this chapter, you should have a standard Scala installation. To get one, go to 
 http://www.scala-lang.org/downloads and follow the directions for your platform. You can also use a Scala plugin-in
 for Eclipse, IntelliJ, or NetBeans. For the steps in this chapter, we'll assume you're using the Scala distribution 
 from [scala-lang.org](http://www.scala-lang.org) .[1]
 
 为了能够运行本章的例子，你应该先安装Scala的标准安装包。可以在http://www.scala-lang.org/downloads 网站下载安装包，根据自己的系统，选择安装向导。
你也可以使用Eclipse、IntelliJ、或者NetBeans的Scala插件。在本章节，我们假设你使用的是从[scala-lang.org](http://www.scala-lang.org)拿到的Scala发布包。

If you are a veteran programmer new to Scala, the next two chapters should give you enough understanding to enable you to start 
writing useful programs in Scala. If you are less experienced, some of the material may seem a bit mysterious to you. But don't 
worry. To get you up to speed quickly, we had to leave out some details. Everything will be explained in a less "fire hose" fashion
in later chapters. In addition, we inserted quite a few footnotes in these next two chapters to point you to later sections of the 
book where you will find more detailed explanations.


如果你是一个新接触Scala的具有编程经验的老鸟，下面两章可以让你具有开始使用Scala编码的能力。如果你没有经验，那么，对于你来说，有一些内容有些神秘了。但是不用担心，
为了让你更快上手，我们省略一些细节。所有的东西都会在后续章节作出解释。另外，我们在后面两章插入了一些脚注，以便在后面的章节找到更详细的解释。

### STEP 1. LEARN TO USE THE SCALA INTERPRETER   第一步：学习使用Scala解释器

The easiest way to get started with Scala is by using the Scala interpreter, an interactive "shell" for writing Scala expressions and programs.
The interpreter, which is called scala, will evaluate expressions you type and print the resulting value. You use it by typing scala at a command
prompt:[2]

开始学习Scala最简单的方法是使用Scala解释器，它是一个可交互的"shell"对于编写Scala表达式或者编程。这个解释器叫做：scala，它会计算你编写的表达式并打印出结果。你可以在命令控制台
编写scala使用它:

```
$ scala
Welcome to Scala 2.12.3 (Java HotSpot(TM) 64-Bit Server VM, Java 1.8.0_121).
Type in expressions for evaluation. Or try :help.

scala>
```
After you type an expression, such as 1 + 2, and hit enter: 之后，你输入一个表达式，例如 1 + 2，然后按回车：
```
scala> 1 + 2
```
The interpreter will print: 解释器将会打印出：
```
res0: Int = 3
```
This line includes:  这行包含以下信息：

-   an automatically generated or user-defined name to refer to the computed value (res0, which means results 0)  一个自动生成或者用户定义的名字，用来展示计算的结果(res0，它的结果是0)
-   a colon(:), followed by the type of the expression(Int)  冒号,以及在它后面的表达式类型：Int
-   an equals sign(=)   等号标识：=
-   the value resulting from evaluating the expression(3)  表达式的计算结果是:3

The type Int names the class Int in the package scala.Packages in Scala are similar to packages in Java: they partition the global namespace and 
provide a mechanism for information hiding[3]. Values of class Int correspond to Java's int values. More generally, all of Java's primitive types 
have corresponding classes in the scala package. For example, scala.Boolean corresponds to Java's boolean. scala.Float corresponds to Java's float.
And when you compile your Scala code to Java byte codes, the Scala compiler will use Java's primitive types where possible to give you the performance
benefits of the primitive types.


这个Int类型，也就是在scala.Packages包中的Int类，在Scala中，它与Java的包相似：他们都可以把全局空间分区，并提供了信息隐藏机制。Int类的值对应Java的int值。更普遍的，Java的所有原始
类型在scala包中都有对应的类。例如：scala.Boolean对应Java的boolean，scala.Float对应Java的float。并且，当你编译你的Scala代码为Java字节码时，Scala的编译器将会使用Java原始类型，
以便尽可能的从原始类型中获取更多的性能。

The resX identifier may be used in later lines. For instance, since res0 was set to 3 previously, res0 * 3 will be 9:

这个resX标识符可能会在以后的行中使用。比如：当上面提到的res0被赋值为3，res0 * 3 将会得到9。
```
scala> res0 * 3
res1: Int = 9
```
To print the necessary, but not sufficient, Hello, world! greeting, type:   为了打印的需要，也不是十分的充足，输入一个打招呼的：Hello, world!:
```
scala> println("Hello, world!")
Hello, world
```
The println function prints the passed string to the standard output, similar to System.out.println in Java.

这个println方法打印传递的字符串到标准输出，就行Java里面的System.out.println。

### STEP 2. DEFINE SOME VARIABLES   第二步，定义一些变量

Scala has two kinds of variables, vals and vars. A val is similar to a final variable in Java. Once initialized, a val can never be reassigned.
A var, by contrast, is similar to a non-final variable in Java. A var can be reassigned throughout its lifetime. Here's a val definition:

Scala有两种类型的变量，vals和vars。这个val就行是Java里面的final变量。一旦初始化，这个val就不能被重新赋值。这个var，作为对比，就像是Java里面的非final变量。在它的生命周期中，
可以被重新的赋值。这里是val变量的定义：
```
scala> val msg = "Hello, world!"
msg: String = Hello, world!
```
This statement introduces msg as a name for the string "Hello, world!". The type of msg is java.lang.String, because Scala strings are implemented
by Java's String class.

这个声明说明msg作为一个字符串“Hello, world!”的名字。这个msg的类型是java.lang.String,因为Scala的字符串是用Java的String类实现的。

If you're used to declaring variables in Java, you'll notice one striking difference here: neither java.lang.String nor String appear anywhere in the
val definition. This example illustrates _type interface_, Scala's ability to figure out types you leave off. In this case, because you initialized
msg with a string literal, Scala inferred the type of msg to be String. When the Scala interpreter(or compiler) can infer types, it is often best to
let it do so rather than fill the code with unnecessary, explicit type annotations. You can, however, specify a type if you wish, and sometimes you 
probably should. An explicit type annotation can both ensure the Scala compiler infers the type you intend, as well as serve as useful documentation
for future readers of the code. In contrast to Java, where you specify a variable's type before its name, in Scala you specify a variable's type after
its name, separated by a colon. For example:

如果你之前用Java声明过变量，你将会注意到一个显著的不同的地方：在使用val定义的地方，没有java.lang.String或者String出现。这个例子说明 _"类型推导"(type interface)_, Scala
具有想象出你省略类型的能力。这里，因为你用字符串字变量初始化了一个msg，Scala推导出这个msg的类型是String。 当Scala的解释器(或者编译器)能推导类型，省略类型将比那些填充一些不必要的
的明确类型注释的代码要好很多。 你可以，如果你愿意定义一个类型，很多时候，你应该这样做。一个明确的类型注释，既可以确保Scala编译器推导出你想要的类型，也可以对将来的读这些代码的人
有很大帮助。对比Java， 你要在变量的前面定义它的类型，而在Scala中，变量的类型在它的名字之后，用冒号作为分隔。比如：

```
scala> val msg2: java.lang.String = "Hello again, world!"
msgs: String = Hello again, world!
```
Or, since java.lang types are visible with their simple names[4] in Scala programs, simply:

或者，因为在Scala程序里，java.lang类型的简化名是可见的，简写为：
```
scala> val msg3: String = "Hello yet again, world!"
msg3: String = Hello yet again, world!
```
Going back to the original msg, now that it is defined, you can use it as you'd expect, for example:

回到这个原来的msg，现在它被定义了，你可以随意使用它，如：
```
scala> println(msg)
Hello, world!
```
What you can't do with msg, give that it is a val, not a var, is reassign it[5]. For example, see how the interpreter complains when you attempt the
following:

什么是不能用msg做的，msg是一个val变量，而不是var，所有不能被重新赋值。例如，如果你尝试使用以下代码修改msg，看一下解释器怎么报错：
```
scala> msg = "Goodbye, cruel world!"
<console>:12: error: reassignment to val
       msg = "Goodbye, cruel world!"
           ^
```
If reassignment is what you want,you'll need to use a var, as in:

如果你想重新赋值，那么你应该使用var，像下面：
````
scala> var greeting = "Hello, world!"
greeting: String = Hello,world!
```` 
Since greeting is a var not a val, you can reassign it later. If you are feeling grouchy later, for example, you could change your greeting to:

因为greeting是一个var而不是val，所以，你可以在以后对它重新赋值。如果你在后面感觉它不好，比如，你可以更改你的greeting：
```
scala> greeting = "Leave me alone, world!"
greeting: String = Leave me alone, world!
```
To enter something into the interpreter that spans multiple lines, just keep typing after the first line. If the code you typed so far is not complete
, the interpreter will respond with a vertical bar on the next line.

为了输入一个跨多行的东西到解释器中，仅仅在第一行后继续编写即可。如果你编写的代码到行尾还没有完成，解释器将会在下一行使用竖线作为回应。
```
scala> val multiLine =
     |   "This is the next line."
multiLine: String = This is the next line.
```
If you realize you have typed something wrong, but the interpreter is still waiting for more input, you can escape by pressing enter twice:

如果你注意到有些你编写错误，但是解释器仍在等待更多的输入，你可以按两次enter键离开。
```
scala> val oops =
       | 
       | 
  You typed two blank lines.  Starting a new command.
  
  scala>
```
In the rest of the book, we'll leave out the vertical bars to make the code easier to read(and easier to copy and paste from the PDF eBook into the interpreter).

在本书的剩余部分，我们将省略掉竖线使代码易读（更容易的从PDF电子书复制粘贴到解释器中）。

###STEP 3. DEFINE SOME FUNCTIONS    第三步，定义一些函数

Now that you've worked with Scala variables, you'll probably want to write some functions. Here's how you do that in Scala:

现在，你已经会使用Scala变量了，你或许想要写一些函数。像这样一样：
```
scala> def max(x: Int, y: Int): Int = {
         if (x > y) x
         else y
       }
max: (x: Int, y: Int)Int
```
Functions definitions start with def. The function's name, in this case max, is followed by a comma separated list of parameters in parentheses.
A type annotation must follow every function parameter, preceded by a colon, because the Scala compiler (and interpreter, but from now on we'll just
say compiler) does not infer function parameter types. In this example, the function named max takes two parameters, x and y, both of type Int. After
the close parenthesis of max's parameter list you'll find another ":Int" type annotation. This one defines the _result type_ of the max function itself.
[6] Following the function's result type is an equals sign and pair of curly braces that contain the body of the function. In this case, the body contains
a single if expression, which selects either x or y, whichever is greater, as the result of the max function. As demonstrated here, Scala's if expression
can result in a value, similar to Java's ternary operator. For example, the Scala expression "if(x>y)x else y" behaves similarly to "(x>y)?x:y" in Java
. The equals sign that precedes the body of a function hints that in the functional world view, a function defines an expression that results in a value.
The basic structure of a function is illustrated in Figure 2.1.

函数使用def开始。函数的名称，这个例子中的max，其后的圆括号中，是一组以逗号分隔的参数列表。使用冒号作为前缀的类型标注必须在函数参数的后面。在这个例子中，函数的名字是max，有两个参数
x和y，它们的类型都是Int。在函数max的参数列表的闭圆括号后，你将会发现另一个 ":Int" 类型注释。这个是定义了max函数的 _结果类型_ 。跟在函数结果类型的后面是一个等号，和一对包含
函数体的大括号。这里，函数体包含了一个if表达式，这个选择x或者y的最大者，最为max的结果。正如我们所看，Scala的if表达式就像Java中的三元表达式一样生成结果。例如，这个Scala的表达式
"if(x>y)x else y" 就像Java的"(x>y)?x:y"。这个函数体前的等号符号提示我们，在函数式的世界里，函数定义是一个可以产生值的表达式。图2.1可以说明函数的基础结构。
![Figure 2.1](img/2.1.png)

**Figure 2.1-The basic form of a function definition in Scala.图2.1-Scala函数定义的基础组成**

Sometimes the Scala compiler will require you to specify the result type of a function. If the function is _recursive_ [7], for example, you must explicitly
specify the function's result type. In the case of max, however, you may leave the result type off and the compiler infer it.[8] Also, if a function consists
of just one statement, you can optionally leave off the curly braces. Thus, you could alternatively write the max function like this:

有时候Scala的编译器会要求你定义函数的结果类型。例如，你必须明确指出递归函数的函数返回值。相反，在max例子中，你可以省去结果类型，并且编译器可以推导出它。同时，如果一个方法仅仅由一段组成，
你可以选择省略大括号。因此，你可以选择像这样写max函数：
```
scala> def max(x: Int, y: Int) = if (x > y) x else y
max: (x: Int, y: Int)Int
```
Once you defined a function, you can call it by name, as in:

一旦你定义了一个函数，你可以通过名字调用他，像这样：
```
scala> max(3, 5)
res4: Int = 5
```
Here's the definition of a function that takes no parameters and returns no interesting result:

这里是一个函数的定义，它没有参数和没有返回值：
```
scala> def greet() = println("Hello, world!")
greet: ()Unit
```
When you define the greet() function, the interpreter will respond with greet: ()Unit. "greet" is, of course, the name of function. The empty parentheses
indicate the function takes no parameters. And Unit is greet's result type. A result type of Unit indicates the function returns no interesting value.
Scala's Unit type is similar to Java's void type; in fact, every void-returning method in Java is mapped to a Unit-returning method in Scala. Methods with
the result type of Unit, therefore, are only executed for their side effects. In the case of greet(), the side effect is a friendly greeting printed to 
the standard output.

当你定义一个greet()函数，这个解释器会回应一个greet: ()Unit。当然，greet是函数的名称。空的括号表明这个函数没有参数。且Unit是greet的结果类型。Unit的结果类型表明，这个函数没有返回值。
Scala的Unit类型就像是Java中的void类型。实际上，Java中的每个空返回值(void-returning)都是对应到Scala中的Unit返回值(Unit-returning)。方法的返回值是Unit，因此，执行它仅仅是为了
它的副作用(side effect)。greet例子，它的副作用是友好的问候被输出到标准输出中。

In the next step, you'll place Scala code in a file and run it as a script. If you wish to exit the interpreter, you can do so by entering :quit or :q.

接下来，你将会在文件中写Scala代码，并作为脚本运行它。如果你想退出解释器，你可以输入:quit或者:q。
```
scala> :quit
$
```  

STEP 4. WRITE SOME SCALA SCRIPTS   第四步， 写Scala脚本

Although Scala is designed to help programmers build very large-scale system, it also scales down nicely to scripting. A script is just a sequence of 
statements in a file that will be executed sequentially. Put this into a file named hello.scala:
尽管Scala的设计是为了帮助程序员构建大的可伸缩的系统，它也可以很好的适应脚本。一个脚本是一个连续的段在一个文件中，会被顺序执行。把这些放到名字为hello.scala的文件中：
```scala
println("Hello, world, from a script!")
```
then run:[9] 然后运行
```
$ scala hello.scala
```
And you should get ye anther greeting:   你会得到另外一个问候：

`Hello, world, from a script`

Command line arguments to a Scala script are available via a Scala array named args. In Scala, arrays are zero based, and you access an element by specifying
an index in parentheses. So the first element in a Scala array named steps is step(0), not steps\[0\], as in Java. To try this out, type the following into
a new file named helloarg.scala:
Scala脚本的命令行参数可以通过名叫args的Scala数组获取。在Scala中，数组从0开始，可以在圆括号中指定一个下标来获取元素。所以Scala的steps数组的第一个元素是steps(0)，而不是Java中的steps\[0\]。
为了验证这个，把下面的输入到helloarg.scala的新文件中：
```scala
// Say hello to the first argument
println("Hello, " + args(0) + "!")
```
then run: 运行:

```
$ scala heloarg.scala planet
```
In this command, "planet" is passed as a command line argument, which is accessed in the script as args(0). Thus you should see:

这个命令，“planet” 作为命令行参数被传递，在脚本里使用args(0)获取值。因此你会看到：

`Hello planet!`

Note that this script included a comment. The scala compiler will ignore characters between // and the next end of line and any characters between /* and */
This example also shows Strings being concatenated with the + operator. The works as you'd expect. The expression "Hello, " + "world!" will result in the
string "Hello, world!".

注意这个脚本包含了一个注释。Scala的编译器会忽略在//到行尾的字符和在/* 与 */ 之间的字符。这个例子也展示了使用+操作符把字符串连接起来。正如你期望的那样运行。这个表达式： "Hello, " + "world!"
将会生成 "Hello, world!" 字符串。

STEP 5. LOOP WITH WHILE; DECIDE WITH IF   While循环，If判断





















