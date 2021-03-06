[参考地址](https://realm.io/cn/news/donn-felker-solid-part-2/)
- 开闭原则意味着，在你的代码设计过程中，你应该**对修改封闭，而对扩展开放**。它的实现思路就是：设计基类，提炼最必要的公共方法，然后使用继承和多态灵活度的组合，对于一些特定的功能，接口插件是非常好的选择。下面描述一个例子： 
  

计算图形面积创建一个图形计算器类AreaComputer，然后传入一个List<Shape>，Shape类的公有方法就是计算逻辑，在AreaComputer中需要调用各个Shape的计算逻辑，而诸如Rectangle、Circle之类的图形，只需要extends Shape，然后在重写Compute()方法来处理各自的计算逻辑就可以了。  
  
  
在Android中，View就完美的实现了之一原则。  

- 在软件迭代中，最好的方式是通过扩展来适应需求的变化。
- 新的特性应该通过新建类来实现。
- 复用老类的功能应该通过继承来实现。
- 要区别老模块的功能，应该通过实现接口来实现。
- 设计类时需要考虑到功能的扩展性。即好的设计，它向外暴露了功能组件的插槽，但你不能去修改其内部构造。通过更换不同的插件来更新功能的实现方式。