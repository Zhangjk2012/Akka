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































