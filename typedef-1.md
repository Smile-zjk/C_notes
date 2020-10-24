# typedef

## struck

结构是C语言中一种用户自定义的可用的数据类型，允许存储不同类型的数据项。（有点像C++和Java中的类，注意只是有点像，区别还是很大的）

使用`struct`语句定义结构体，格式如下

```c
struct tag { 
    member-list
    member-list 
    member-list  
    ...
} variable-list ;
```

**tag**是结构体标签。

**member-list**是标准的变量定义。

**variable-list**是结构变量。

在一般情况下，**tag、member-list、variable-list** 这 3 部分至少要出现 2 个。

```c
//此声明声明了拥有3个成员的结构体，分别为整型的a，字符型的b和双精度的c
//同时又声明了结构体变量s1
//这个结构体并没有标明其标签
struct 
{
    int a;
    char b;
    double c;
} s1;

//此声明声明了拥有3个成员的结构体，分别为整型的a，字符型的b和双精度的c
//结构体的标签被命名为SIMPLE,没有声明变量
struct SIMPLE
{
    int a;
    char b;
    double c;
};
//用SIMPLE标签的结构体，另外声明了变量t1、t2、t3
struct SIMPLE t1, t2[20], *t3;

//也可以用typedef创建新类型
typedef struct
{
    int a;
    char b;
    double c; 
} Simple2;
//现在可以用Simple2作为类型声明新的结构体变量
Simple2 u1, u2[20], *u3;
```

## typedef

typedef关键字，为**类型**取一个新的名字.

```c
typedef unsigned char BYTE; // 为单字节数定义了一个术语BYTE
// BYTE可作为类型unsigned char的缩写
BYTE a1;
unsigned char a2;
```

可以对结构体使用typedef来定义一个新的数据类型名字，然后使用这个新的数据类型来直接定义结构变量

```c
typedef struct Books
{
  char title[20];
  char author[6];
  int book_id;
} Book;

int main()
{
  Book book; //Book 是结构体Books的一个新的名字
  Books book;  
}
```

**\#define** 是 C 指令，用于为各种数据类型定义别名，与 **typedef** 类似，但是它们有以下几点不同：

* **typedef** 仅限于为`类型`定义符号名称，**\#define** 不仅可以为类型定义别名，也能为数值定义别名，比如您可以定义 1 为 ONE。
* **typedef** 是由`编译器执行解释`的，**\#define** 语句是由`预编译器进行处理`的。

## enum

枚举是 C 语言中的一种基本数据类型,枚举语法定义格式为：

```c
enum　枚举名　{枚举元素1,枚举元素2,……};
```

```c
enum DAY
{
      MON=1, TUE, WED, THU, FRI, SAT, SUN
};
```

**注意：**第一个枚举成员的默认值为整型的 0，后续枚举成员的值在前一个成员上加 1。在这个实例中把第一个枚举成员的值定义为 1，第二个就为 2，以此类推。

