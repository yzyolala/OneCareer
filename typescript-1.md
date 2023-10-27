## 类型 
这段代码介绍了 TypeScript 中的类型操作，特别是如何使用 Omit 和 Partial 这两个实用类型。具体来说：

首先，定义了一个名为 todo1 的常量，并为其分配了 Todo 类型的对象。这个 Todo 类型应该包含 id、title、description 和 deadline 这四个属性，但在这段代码中没有显示 Todo 类型的定义。

接着，定义了一个名为 TodoNeverDue 的新类型，它使用 Omit 实用类型从原始 Todo 类型中排除了 deadline 属性。这意味着 TodoNeverDue 类型的对象不应该有 deadline 属性。

然后，定义了另一个名为 TodoNeverDue2 的新类型，它使用 Partial 实用类型。Partial 实用类型将 Todo 类型中的所有属性都变为可选的。这意味着 TodoNeverDue2 类型的对象可以有或没有 Todo 类型中的任何属性。

总的来说，这段代码演示了如何使用 Omit 和 Partial 实用类型来创建新的派生类型。这两种实用类型都允许你基于现有的类型创建新的类型，但它们的目的和用途是不同的。
```typescripte
const todo1:Todo={
    id:1,
    title:"buy milk",
    description:"buy milk at 5 pm",
    deadline: new Date()

}

type TodoNeverDue=Omit<Todo,'deadline'>;
type TodoNeverDue2=Partial<Todo>;
```

## 函数
```typescripte
function hello1(name:string):string{
    console.log(name);
    return name;
}

function hello2(name:string){
    console.log(name);
    return name;
}

const hello3=function(name:string):void{
    console.log(name);
}

const hello4=(name:string)=>{
    console.log(name);
}

const hello5=(name:string):number=>{
    console.log(name);
    return name.length;
}
```
这几种写法区别是什么

你展示了五种定义函数的方式，它们之间的主要区别是函数的声明方式、函数的箭头形式和返回值类型。以下是对这几种写法的详细比较：

函数声明 (hello1 和 hello2):

使用function关键字进行函数声明。
hello1和hello2在功能上是相同的，但hello1明确地指定了返回值类型为string，而hello2利用TypeScript的类型推断来确定返回值类型（在这种情况下也是string）。
函数表达式 (hello3 和 hello4):

这两个函数是使用函数表达式定义的，也就是将一个匿名函数赋值给一个变量。
hello3使用了传统的函数表达式形式，并明确指定了返回值类型为void，表示此函数不返回任何值。
hello4使用了ES6的箭头函数形式。由于没有明确指定返回类型，并且该函数只是执行了一个console.log语句，TypeScript会将其返回类型推断为void。
箭头函数 (hello5):

使用ES6的箭头函数形式定义。
明确指定了返回值类型为number。
函数体中返回了name的长度，这是一个数字，与声明的返回类型number匹配。
总结一下主要的区别：

函数声明 vs. 函数表达式：前者使用function关键字并直接为函数命名；后者将一个匿名函数赋值给一个变量。
箭头函数 vs. 传统函数：箭头函数有更简洁的语法，没有自己的this、arguments、super或new.target，而传统函数则有。
返回值类型：可以明确指定，也可以让TypeScript自动推断。
在实际开发中，根据具体的使用场景和团队的编码约定选择合适的函数定义方式。

## 多态
```typescripte
// 定义一个“动物”类
class Animal {
    name: string; // 动物的名称属性

    // 构造函数，用于创建动物对象时设置其名称
    constructor(name: string) {
        this.name = name;
    }

    // 动物的移动方法
    move() {
        console.log("hello");
    }
}

// 定义一个“狗”类，它继承自“动物”类
class Dog extends Animal {
    furColor: string; // 狗的毛色属性

    // 构造函数，用于创建狗对象时设置其名称和毛色
    constructor(name: string, furColor: string) {
        super(name); // 调用父类“动物”的构造函数来设置名称
        this.furColor = furColor; // 设置毛色
    }

    // 重写动物的移动方法，使其更具体地描述狗的移动方式
    move() {
        console.log(`${this.name} is running`);
    }

    // 狗类的静态方法，用于描述狗的叫声
    static bark() {
        console.log(`barking`);
    }
}

// 创建一个名为“horse”的动物对象
const horse = new Animal('horse');
horse.move(); // 调用动物的移动方法

// 创建一个名为“Beibei”的狗对象，其毛色为“golded”
const Beibei = new Dog('Beibei', 'golded');
Beibei.move(); // 调用狗的移动方法
Dog.bark(); // 调用狗的叫声方法
```

## React Native (RN)简介：

**RN (React Native)** 是一个跨平台的 UI 开发框架，支持 **iOS**、**Android** 和 **web**。在移动开发中，RN 的角色与 `react-dom` 在 web 中的角色相似，即渲染。

**React** 是一个用于构建 UI 的平台无关库。它提供了状态和组件生命周期管理的钩子。

### 优势：

- 在一个代码库中维护多个平台的应用程序
- 容易应用我们的 JS/TS 和 web 前端开发知识

### 在RN中编写的著名应用程序：

- Facebook
- MS Office
- Tesla
- Pinterest
- JD
- Baidu
- QQ

**React Native (RN) 是如何工作的?**

- 该桥接技术将 JS 转换为特定平台的组件（例如，JS 转为 Swift/Object-C/Java/Kotlin）。
- UI 元素被编译为原生视图。
- 应用程序逻辑在 JS 线程上运行。

---

**对比表**：

| React Native UI 组件 | Android 视图 | iOS 视图 | Web 对应项 | 描述 |
|----------------------|-------------|----------|-----------|------|
| &lt;View&gt;            | &lt;ViewGroup&gt;| &lt;UIView&gt; | 一个不滚动的 &lt;div&gt; | 一个支持flexbox、样式、某些触摸处理和可访问性控制的容器 |
| &lt;Text&gt;            | &lt;TextView&gt; | &lt;UITextView&gt; | &lt;p&gt; | 显示、样式化、嵌套文本串，甚至处理触摸事件 |
| &lt;Image&gt;           | &lt;ImageView&gt;| &lt;UIImageView&gt; | &lt;img&gt; | 显示不同类型的图像 |
| &lt;ScrollView&gt;      | &lt;ScrollView&gt;| &lt;UIScrollView&gt; | &lt;div&gt; | 一个可以包含多个组件和视图的通用滚动容器 |
| &lt;TextInput&gt;       | &lt;EditText&gt; | &lt;UITextField&gt; | &lt;input type="text"&gt; | 允许用户输入文本 |


## 前端代码实例
```typescripte
// 引入 react-native 库中的组件
import { Text, SafeAreaView, View,StyleSheet,Button } from 'react-native';

// 定义一个全局变量
let myVal="apple"

// 定义一个默认导出的函数组件
export default function App() {

  // 在组件内部定义一个局部变量
  let myVal2="banana"

  // 返回 JSX
  return (
    <SafeAreaView style={styles.container}>
      {/* 使用三元运算符在文本中进行条件判断 */}
      <Text>My first RN App {3>10?'bigger':'smaller'}</Text>
      {/* 在文本中插入变量的值 */}
      <Text>My first RN App {myVal2}</Text>
      {/* 使用内联样式 */}
      <View style={{backgroundColor:'green',height:'500px',width:'200px',paddingTop:20,paddingLeft:10,marginBottom:50,marginTop:100,borderWidth:3,borderColor:'blue',flexDirection:'column',justifyContent:'flex-end',alignItems:'center'}}>
        {/* 设置文本的颜色 */}
        <Text style={{color:'yellow'}}>children 1</Text>
        <Text>children 2</Text>
        <Text>children 3</Text>
      </View>
      {/* 定义一个按钮并设置它的点击事件 */}
      <Button title="my button" onPress={()=>{
        console.log("press...")
      }}/>
    </SafeAreaView>
  );
}

// 使用 StyleSheet.create 来定义样式
const styles = StyleSheet.create({
  container: {
    flex: 1,
    // 下面的代码被注释掉了
    // justifyContent: 'center',
    // backgroundColor: 'red',
    // padding: 8,
  }
});
```

简要总结：

引入了必要的 React Native 组件。
定义了一个名为 App 的函数组件。
使用了三元运算符进行条件渲染。
使用了内联样式和 StyleSheet 定义的样式。
在 JSX 中插入了变量的值。
为 Button 组件设置了点击事件处理函数。



