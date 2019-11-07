## 函数
- 函数：
    - 普通函数：运行函数中的代码，为了复用
    -构造函数（class）

        this实例
        默认return  实例
        在类里面一般都是添加属性

        new 构造函数

        原型和原型链：
            函数走原型  （构造函数的实例）
            实例走链  （实例找不到某个属性或者方法就走）

            实例的原型链 === 构造函数的原型

        实例
            new Function -> function

## this的三种改变方法
- call（that，多个）
- apply（that，两个）
- bind（that，多个）
    - 共同特点都是，第一个参数都是改变this指向的，函数天生自带的
    - null,undefined（无效的）传了都是window

    1.this是实例
    2.默认return 实例，如果return为引用类型就为引用类型
    3.实例的原型链 === 构造函数的原型
    4.可以不加括号调用

## class类名
- class 

        类名 {
            constructor(){
                给自身添加属性或者方法，就必须要写constructor
            }
        }

## call的使用
- 所有的数据都有一个toString的方法，但是写法是不一样的唯独Object的toString能够去检测当前的数据类型，所以可以把this改变，达到我们的目的

- Array的toString，除了数组本身别的也都能检测数据类型

- 为什么call this就能借到某个方法？
    - 因为这些方法内部使用的数据都是this
    - Array.from()  把类数组转数组


## 解构赋值
- 数组的结构赋值：
    - let [x,y] = [a]

    声明的时候一定要是个数组，左右两边的结构保持一致

- let {key1,key2} = {key1:val1,key2:val2}
    - 在声明的时候用块声明，块中放对象的key值，这里的key值一定要和解构对象的key值名字要一致

    - 如果要取别名，使用:新定义的名字即可
        - let{key1:k,key2} = {key1:val1,key2:val2}

    - 此时key1已经访问不到了，要访问就报错，只能访问k，k就代表key1，名字跟声明变量规则一致

    - 如果加了:不报错，那么可以先结构一次，在重命名
        ```
        let {
            f,
            f:x
        } = {
            f:{
                name:'11',
                age:22
            }
        }
        ```