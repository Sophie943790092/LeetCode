# Java 基础语法
## for 循环
1. 使用分号做分隔, 直接在for循环中循环变量做define和assign；
2. return后有分号
```java
for(int index = 0; index < nums.length; index++) {
        if(target == nums[index]) {
            return index;
        }
}
```
## return的作用
结束函数执行，并返回一个值（如果指定的话）。
## 数组
java数组是固定长度的，一旦声明后大小就不能改变
### 赋值
在同一句里完成分配 + 赋值:
```java
int[] nums = new int[] {1, 2, 3, 4, 5};
```
具体应用：
```java
public int[] searchRange(int[] nums, int target) {
        int leftIndex = findFirstPosition(nums, target);
        int rightIndex = findLastPosition(nums, target);

        return new int[]{leftIndex, rightIndex};//❣️
    }
```
### 数组元素同质性
Java 数组在声明时就确定了组件类型（component type），在编译和运行时都会对数组元素类型做检查。<br>
对于**基本类型数组**：只能存**同一种**基本类型元素。<br>
对于引用类型数组：可以存放“声明类型”本身或其子类（多态），但不能存与之无关的类型对象。
## 常用内置属性或函数
1. `nums.length`:在 Java 中，**数组**的长度是一个属性 nums.length，而不是方法 nums.length()。因此需要去掉括号并使用 nums.length

## Java除法
1. 整数除法（/，整数类型）
**特性**：
* 当两个操作数都是整数时，结果是整数，会执行向零取整。
* 即使结果是小数部分，会自动舍去小数部分，只保留整数部分。
```java
int a = 7, b = 3;
int result = a / b; // 结果是 2，而不是 2.3333
System.out.println(result); // 输出 2
```
**注意**：

结果向零取整：这意味着，无论结果是正数还是负数，都会舍去小数部分。例如：

`5 / 2 = 2`

`-5 / 2 = -2`（这与数学上的舍入不同）


2. 浮点数除法（/，浮点类型）
**特性**：

当 **任一操作数是浮点数（float 或 double）**时，结果是浮点数，会保留小数部分。

浮点除法不会舍去小数部分，而是返回精确结果。

**例子**：
```java
double a = 7.0, b = 3.0;
double result = a / b; // 结果是 2.3333...
System.out.println(result); // 输出 2.3333333333333335
```
**注意**：

浮点类型（float 和 double）可以返回近似值，由于浮点数的表示方法存在精度误差，所以计算时可能出现很小的偏差。

3. 取余运算（%，整数类型）
**特性**：

取余运算符 % 用于返回两个数相除后的余数。

该操作符也有整数和浮点类型的区别，且遵循不同的取余规则。

**例子**：
```java
int a = 7, b = 3;
int result = a % b; // 结果是 1，7 除以 3 的余数是 1
System.out.println(result); // 输出 1
```
* 浮点数取余：
```java
double a = 7.5, b = 2.0;
double result = a % b; // 结果是 1.5，7.5 除以 2 的余数是 1.5
System.out.println(result); // 输出 1.5
```
**特别注意**：
取余运算的符号：对于负数，取余的符号由被除数（即操作符左边的数）决定。

`7 % 3 = 1`（正数）

`-7 % 3 = -1`（负数）

## 自增运算符
在Java（和大多数C系语言）里：

* `p++` 叫后置自增运算符，意思是**先使用p的当前值，然后再让p加1**。
* `++p` 叫前置自增运算符，意思是**先让p加1，然后再使用它的新值**。

举个例子：
```java
int p = 0;
System.out.println(p++); //输出0， 执行完后p变成1
System.out.println(p); //输出1

p = 0;
System.out.println(++p); //输出1（先加 1，再输出）
```
## 哈希表
Java里哈希表常用的类是HashMap<K, V>, 其中：
* K 是 key键的类型
* V 是 value值的类型

**声明&新建哈希表**
```java
//键是Interger， 值是String
Map<Integer, String> map = new HashMap<>();
```
常用导入：
```java
import java.util.HashMap;
import java.util.Map;
```

**插入元素**
```java
map.put(key, value);//插入一个键值对
```
示例：
```java
map.put(1, "apple");
map.put(2, "banana");
```
**注意**：如果key已经存在，put会覆盖原来的值。

**查找元素**
```java
map.containsKey(key) //判断key是否存在
map.get(key)  //根据key获取value（如果不存在则返回null）
```
示例：
```java
if(map.containsKey(2)){
    System.out.println(map.get(2)); //输出banana
}
```
**更新元素**

直接使用put就行，因为HashMap会覆盖已有的值

**删除元素**
```java
map.remove(key);
```
