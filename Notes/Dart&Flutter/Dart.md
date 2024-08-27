# Dart语法

## 数据类型

### 基本数据类型
	//整型
	int
	//双精度
	doubel
	//布尔
	bool
	//字符串
	String
	//强类型
	var

### List

	//定义
	var list = ["1","2"];
	//指定类型
	var list = <Srting>["1","2"];
	//固定长度List
	var list = List.filled(length,fill);
	//固定长度List指定类型
	var list = List<Srting>.filled(length,fill);
	//添加一个数据
	list.add("3");
	//添加多个数据
	list.addAll(["4","5"]);
	//获取长度
	list.length;
	//获取数据索引
	list.indexOf("1");
	//删除数据
	list.remove("5");
	list.removeAt(index);

### Map
	//定义
	//1
	var map = {
	  "name" = "testName";
	  "num" = 123;
	};
	//2
	var map = new Map();
	map["name"] = "testName";
	map["num"] = 123;
	
	//取内容
	map["name"];
	
	//增加
	map.addAll({
	  "type" = 1;
	})
	
	//删除
	map.remove(key);

### 类型转换
	//将String转换为Number
	//1、转为int
	String str = "1234";
	int a = int.parse(str);
	//2、转为doubel
	String str = "12.34";
	doubel a = doubel.parse(str);
	
	//将Number转换为String
	int a = 1234;
	String str = a.toString();

## 类
+ 所有对象都继承Object
+ 类名用大驼峰命名法

### 抽象类
+ 用abstract修饰
+ 子类继承必须实现抽象方法
+ 抽象类作为接口必须实现抽象类中的所有属性和方法
+ 抽象类不能被实例化，继承它的子类可以

### 接口
+ 没有interface关键字定义
+ 用implements关键字实现

### Mixins
+ 只继承Object
+ 没有构造函数
+ 不是接口，不是继承