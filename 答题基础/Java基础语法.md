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