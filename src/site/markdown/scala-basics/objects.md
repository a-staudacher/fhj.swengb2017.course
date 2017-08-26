## Objects

### Standalone Objects

In Scala, one can define objects which follow the [singleton pattern](https://en.wikipedia.org/wiki/Singleton_pattern)  very easily.

~~~
object Foo {

  val MyConstant = 1
  
}

println(Foo.MyConstant)
~~~

If you need a namespace without much fuzz, you can define an _object_ and have some place to put constants for example. 

### Companion Objects

Bear in mind that you can define a _class_ and an _object_ with the same name. If this is the case, we speak about so called _companion objects_. Companion objects and its accompanying class must reside in the same file. The class is then called _companion class_. 

~~~
case class Foo(a : Int)
object Foo {

 def apply() : Foo = Foo(10)
 
}

Foo()    
~~~

Companion objects, among other things, serve as a place to put constructor methods. Constructor methods have, by convention, the name _apply_, In the example above we have introduced a constructor for the _Foo_ class without any parameters. The implementation above instantiates a _Foo_ class instance with a default value for _a = 10_. 

### Case Objects

We have already learned about _case classes_, which extend normal classes with special behavior and additional functionality. One could say something similar exists for objects, the so called _case objects_.

Here is an example for a case object:

~~~
case object Foo
~~~

We don't gain much by defining a _case object_ as opposed to a normal _object_, the former can be serialized, the latter can not. 