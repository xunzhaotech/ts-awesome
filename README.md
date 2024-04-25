# ts-awesome
#### JavaScript的数据类型（普及）
JavaScript的数据类型有8种，在ES5的时候，我们认知的数据类型是6种，Number、Null、Undefined、Boolean、String、Object。ES6中新增一种Symbol，这种类型的对象永不相等，即使创建的时候传入相同的值，可以解决属性名冲突的问题，作为标记。谷歌还出现一种bigint。是指安全存储、操作大整数。（很多人不把这个作为数据类型）。
## 学习目录
创建一个 TypeScript 从入门到精通的学习提纲，可以帮助学习者系统地掌握 TypeScript 的核心概念和应用。这个提纲覆盖了从基础到高级的 TypeScript 知识，旨在帮助学习者逐步深入理解 TypeScript，并在实际项目中应用所学知识。随着 TypeScript 的不断发展，这个提纲也可以根据新的功能和最佳实践进行更新。以下是一个建议的学习提纲：

### TypeScript 入门
1. **TypeScript 简介**
   - 什么是 TypeScript
   - TypeScript 与 JavaScript 的关系
   - 为什么选择 TypeScript

2. **环境搭建**
   - 安装 Node.js 和 npm
   - 安装 TypeScript 编译器

3. **基础语法**
   - 类型注解
   - 接口（Interfaces）
   - 类（Classes）
   - 函数（Functions）

4. **类型系统**
   - 基本类型
   - 复杂类型：联合类型、交叉类型
   - 类型别名（Type Aliases）
   - 泛型（Generics）

5. **面向对象编程**
   - 继承（Inheritance）
   - 封装（Encapsulation）
   - 多态（Polymorphism）

### TypeScript 进阶
6. **模块化编程**
   - ES6 模块与 CommonJS 模块
   - TypeScript 的模块系统

7. **高级类型**
   - 索引类型（Indexed Types）
   - 条件类型（Conditional Types）
   - 高级类型守卫

8. **装饰器（Decorators）**
   - 类装饰器
   - 方法装饰器
   - 访问器装饰器

9. **模块与命名空间**
   - 模块的导入与导出
   - 命名空间的使用

10. **配置文件 tsconfig.json**
    - 配置编译选项
    - 配置源代码管理

### TypeScript 实战
11. **项目结构**
    - 项目目录结构设计
    - 模块化管理

12. **与前端框架的整合**
    - React + TypeScript
    - Angular + TypeScript
    - Vue + TypeScript

13. **代码重构**
    - 利用 TypeScript 进行代码重构
    - 代码质量提升

14. **测试**
    - TypeScript 与单元测试
    - 集成测试

15. **性能优化**
    - TypeScript 编译选项优化
    - 运行时性能考虑

### TypeScript 高级应用
16. **构建工具与任务自动化**
    - 使用 Gulp 或 Grunt
    - 使用 Webpack 或 Rollup

17. **自定义类型守卫与类型断言**
    - 创建自定义类型守卫
    - 类型断言的应用

18. **类型推断**
    - TypeScript 的类型推断机制
    - 优化类型推断

19. **代码规范与最佳实践**
    - TSLint 或 ESLint 的使用
    - 代码风格指南

20. **社区与资源**
    - 参与 TypeScript 社区
    - 阅读和贡献开源项目

21. **案例研究**
    - 分析实际项目中的 TypeScript 应用
    - 学习业界最佳实践

### TypeScript 专家级
22. **深入 TypeScript 编译器**
    - 理解 TypeScript 编译器工作原理
    - 编译器插件开发

23. **语言服务与编辑器集成**
    - TypeScript 语言服务 API
    - VSCode 插件开发

24. **大型项目实战**
    - 参与大型项目开发
    - 解决复杂业务逻辑

25. **持续学习**
    - 关注 TypeScript 官方动态
    - 学习最新的 TypeScript 特性
##### 基本类型(单类型)
- String
- Number
- Boolean
- Null
- Undefined
- Symbol（ES6）
- bigInt
##### 引用类型
- Object（function、Array、Date）
#### TypeScript从入门到精通
- [ ] 【第1节】 TypeScript环境安装
- [X] 【第2节】 TypeScript基本类型（String）
- [X] 【第3节】 TypeScript基本类型 （Number）
- [X] 【第4节】 TypeScript基本类型（Boolean）
- [X] 【第4节】 TypeScript基本类型（Null）
- [X] 【第4节】 TypeScript基本类型（Boolean）
- [X] 【第5节】 TypeScript特殊类型（Undefined）
- [X] 【第6节】 TypeScript扩展类型（Tuple）
#### 学习链接
- [快智岛](https://xunzhaotech.gitee.io/kuaizhidao/)
#### 开源推荐

## 一、前言
我们都知道TypeScript是JavaScript的超集,在学习TypeScript之前自然绕不过JavaScript，在小编看来，学习任何一门语言最快的方法就是对比差异学习，而学习TypeScript关键就是**基本类型、特殊类型和扩展类型**。
## 二、基本类型合集
### 2.1 数字类型
```javascript
// 数字，二、八、十六进制都支持
let decLiteral: number = 6;
let hexLiteral: number = 0xf00d;
```
### 2.2 字符串
```javascript
// 字符串，单双引都行
let name: string = "互联网看视界";
let sentence: string = `Hello, my name is ${ name }.
```
### 2.3 数组
```javascript
// 数组，第二种方式是使用数组泛型，Array<元素类型>：
let list: number[] = [1, 2, 3];
let list: Array<number> = [1, 2, 3];
```
### 2.4 undefined
```javascript
let u: undefined = undefined;
```
### 2.5 null
```javascript
let n: null = null;
```
## 三、特殊类型
### 3.1 元组 Tuple
> 元组 作为有组织的数组，你需要以正确的顺序预定义数据类型。如果不遵循 为元组 预设排序的索引规则，那么 Typescript 会警告。
```javascript
const messyArray = [' something', 2, true, undefined, null];
const tuple: [number, string, string] = [24, "Indrek" , "Lasn"]
```
### 3.2 枚举 Enum 
> enum 类型是对JavaScript标准数据类型的一个补充。 像C#等其它语言一样，使用枚举类型可以为一组数值赋予友好的名字。
```javascript
// 默认情况从0开始为元素编号，也可手动为1开始
enum Color {Red = 1, Green = 2, Blue = 4}
let c: Color = Color.Green;
 
let colorName: string = Color[2];
console.log(colorName); // 输出'Green'因为上面代码里它的值是2
// 存储状态
enum AppStates {
 hasErrots,
 isFetching,
 isUnstLogindIn,
 docesUsetHaveProfileImage
}
```
### 3.3 Void
> 在 Typescript 中， 你必须在函数中定义返回类型,若没有返回值，则会报错,我们可以将其返回值定义为 void, 此时将无法 return。
```javascript
// 函数申明
function setName(name:string):void{
 this.name = name;
}
// 表达式申明
const sayName = function (name:string):void {
   setName(name)
 }
```
### 3.4 Any类型
> 当你无法确认在处理什么类型时可以用这个，但要慎重使用，用多了就失去使用TS的意义（接入接入第三方库用的比较多）。
```javascript
let person: any = "互联网看视界"
person = 25
person = true
```
### 3.5 Never
> 无法预期的结果。
```javascript
throw new Error(message)
return error("Something failed")
while (true) {} /
```
## 四、扩展类型
### 4.1 类型断言
有时，您会获得有关 TypeScript 不知道的值类型的信息。可以用来手动指定一个值的类型。
- 有两种写法，尖括号和 as 
```javascript
let someValue: any = "this is a string";
 
let strLength: number = (<string>someValue).length;
let strLength: number = (someValue as string).length;
```
当 TypeScript 不确定一个联合类型的变量到底是哪个类型的时候，我们只能访问此联合类型的所有类型里共有的属性或方法：
```javascript
function getLength(something: string | number): number {
 return something.length;
}
 
// index.ts(2,22): error TS2339: Property 'length' does not exist on type 'string | number'.
// Property 'length' does not exist on type 'number'.
```

### 2.1 数字类型
```javascript
// 数字，二、八、十六进制都支持
let decLiteral: number = 6;
let hexLiteral: number = 0xf00d;
```
### 2.2 字符串
```javascript
// 字符串，单双引都行
let name: string = "互联网看视界";
let sentence: string = `Hello, my name is ${ name }.
```
### 2.3 数组
```javascript
// 数组，第二种方式是使用数组泛型，Array<元素类型>：
let list: number[] = [1, 2, 3];
let list: Array<number> = [1, 2, 3];
```
### 2.4 undefined
```javascript
let u: undefined = undefined;
```
### 2.5 null
```javascript
let n: null = null;
```
## 三、特殊类型
### 3.1 元组 Tuple
> 元组 作为有组织的数组，你需要以正确的顺序预定义数据类型。如果不遵循 为元组 预设排序的索引规则，那么 Typescript 会警告。
```javascript
const messyArray = [' something', 2, true, undefined, null];
const tuple: [number, string, string] = [24, "Indrek" , "Lasn"]
```
### 3.2 枚举 Enum 
> enum 类型是对JavaScript标准数据类型的一个补充。 像C#等其它语言一样，使用枚举类型可以为一组数值赋予友好的名字。
```javascript
// 默认情况从0开始为元素编号，也可手动为1开始
enum Color {Red = 1, Green = 2, Blue = 4}
let c: Color = Color.Green;
 
let colorName: string = Color[2];
console.log(colorName); // 输出'Green'因为上面代码里它的值是2
// 存储状态
enum AppStates {
 hasErrots,
 isFetching,
 isUnstLogindIn,
 docesUsetHaveProfileImage
}
```
### 3.3 Void
> 在 Typescript 中， 你必须在函数中定义返回类型,若没有返回值，则会报错,我们可以将其返回值定义为 void, 此时将无法 return。
```javascript
// 函数申明
function setName(name:string):void{
 this.name = name;
}
// 表达式申明
const sayName = function (name:string):void {
   setName(name)
 }
```
### 3.4 Any类型
> 当你无法确认在处理什么类型时可以用这个，但要慎重使用，用多了就失去使用TS的意义（接入接入第三方库用的比较多）。
```javascript
let person: any = "互联网看视界"
person = 25
person = true
```
### 3.5 Never
> 无法预期的结果。
```javascript
throw new Error(message)
return error("Something failed")
while (true) {} /
```
## 四、扩展类型
### 4.1 类型断言
有时，您会获得有关 TypeScript 不知道的值类型的信息。可以用来手动指定一个值的类型。
- 有两种写法，尖括号和 as 
```javascript
let someValue: any = "this is a string";
 
let strLength: number = (<string>someValue).length;
let strLength: number = (someValue as string).length;
```
当 TypeScript 不确定一个联合类型的变量到底是哪个类型的时候，我们只能访问此联合类型的所有类型里共有的属性或方法：
```javascript
function getLength(something: string | number): number {
 return something.length;
}
 
// index.ts(2,22): error TS2339: Property 'length' does not exist on type 'string | number'.
// Property 'length' does not exist on type 'number'.
```




