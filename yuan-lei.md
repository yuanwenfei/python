# 元类

元类：用于创建类\(对象\)的类。也可以理解为：元类就是类的类

python中提供了type\(\)内建函数来创建类。

## &lt;1&gt;type动态创建类

通过type我们可以动态的创建类。

type语法：

```
type(类名, 由父类名称组成的元组（针对继承的情况，可以为空），包含属性的字典（名称和值）)
```

如：

```
Test2 = type("Test2",(),{}) #定了一个Test2类
In [5]: Test2() #创建了一个Test2类的实例对象
Out[5]: <__main__.Test2 at 0x10d406b38>
```

以上代码：通过type动态的创建了一个Test2类。

### &lt;2&gt;使用type创建含有继承关系的类 {#4-使用type创建带有属性的类}

```
>>> Foo = type('Foo', (), {})  # 父类
```

```
>>> FooChild = type('FooChild', (Foo,),{})  # 子类 继承 Foo
```

#### 注意： {#注意：}

* type的第2个参数，元组中是_**父类的名字，而不是字符串**_

### &lt;3&gt;使用type创建带有属性的类 {#4-使用type创建带有属性的类}

type 接受一个字典来为类定义属性，因此:

```
>>> Foo = type('Foo', (), {'bar':True})
```

可以翻译为：

```
>>> class Foo(object):
…       bar = True
```

并且可以将Foo当成一个普通的类一样使用：

```
>>> print Foo
<class '__main__.Foo'>
>>> print Foo.bar
True
>>> f = Foo()
>>> print f
<__main__.Foo object at 0x8a9b84c>
>>> print f.bar
True
```

#### 注意： {#注意：}

* 添加的属性是_**类属性**_，并不是实例属性


