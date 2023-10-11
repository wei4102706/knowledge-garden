`Extends`用于从另一个类继承，而`Implements`用于实现接口。

- 类只能继承一个父类，但可以实现多个接口。
- 使用`extends`继承父类时，可以重写父类的方法，并可以调用父类的非私有方法。
- 使用`implements`实现接口时，必须提供接口中所有声明方法的实现。


Interface Inheritance
	Method name only, no implementation: Interface methods can not have body
Implementation Inheritance
	Default method implementation
	add `default` keyword in interface method 
