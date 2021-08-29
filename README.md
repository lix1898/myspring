# mySpring- 手写spring
最简易的流程，省去了 beanFactory 以及循环依赖等流程，仅是个demo，有利于熟悉spring的正常流程

## mySpring 流程
* 入口 annotationConfigApplicationContext 注解配置解析器，传入配置，要扫描的包
* 接下来： 
> 1、就是扫描包，扫描配置的包下面的所有类
> 2、遍历 需要交给容器管理的类，生成 beanDefinition 对象，并给benDefinition 对象，并 设置 scope 放入容器中
> 3、遍历 benDefinition ，根据  benDefinition 创建对象
> 4 创建对象的过程中分为
> 4.1 实例化
> 4.2 填充属性 自动注入
> 4.3 设置 aware 接口中的属性
> 4.4 执行 BeanPostProcessor before 方法
> 4.5 执行 实现了 InitializingBean 接口的中 初始化对象的方法 afterPropertiesSet
> 4.7 执行 BeanPostProcessor after 方法
> 4.8 返回bean



