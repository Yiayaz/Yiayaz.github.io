---
title: C++ Prime 5
date: 2021-04-05 21:42:00
categories:
- C++
tags:
- C++
---



**<center>C++ Prime 5</center>**

<!--more-->

# 习题部分

[Reference linking 1](https://github.com/Mooophy/Cpp-Primer)

[Reference linking 2](https://github.com/fsaadatmand/Cpp-Primer)

## 第一章

### 1.9

~~~C++
#include <iostream>
using namespace std;
int main(){
    int i = 50;
    int ans = 0;
    while(i <= 100) ans = i++;
    cout << ans;
    return 0;
}
~~~

### 1.10

~~~c++
#include <iostream>
using namespace std;
int main(){
    int i = 10;
    while(i >= 0)cout << i-- <<" ";
    return 0;
}
~~~

### 1.11

~~~C++
#include <iostream>
using namespace std;
void swap(int &a,int &b){
    int t = a;
    a = b;
    b = t;
}
int main(){
    printf("please input two integers\n");
    int i, j;
    cin >> i >> j;
    if(i > j) swap(i,j);
    while(i <= j) cout << i++ << " ";
    return 0;
}
~~~

### 1.12

~~~C++
int sum = 0;
for (int i = -100; i <= 100; ++i) sum += i;
//实际上就是从-100加到100，sum为0
~~~

### 1.14

实际上表达能力是一样的, 如果按照规范来写for循环,可以尽量缩小局部变量的作用范围.

for 循环和 while 循环会在 loop statement 前多做一次 conditional jump, do while 则不会.

### 1.16

~~~C++
#include <iostream>
using namespace std;
int main(){
    int sum = 0;
    int num;
    while(~scanf("%d", &num)){
        sum += num;
        cout << sum <<endl;
    }
    return 0;
}
~~~

## 第二章

### 2.1

C++ guarantees short and int is at least 16 bits, long at least 32 bits, long long at least 64 bits.
The signed can represent positive numbers, negative numbers and zero, while unsigned can only represent numbers no less than zero.
The C and C++ standards do not specify the representation of float, double and long double. It is possible that all three implemented as IEEE double-precision.

### 2.2

use double, or also float.

### 2.3 & 2.4

在表达式内如果有了无符号数，最后是一个负值，那么编译器会取模。

### 2.5 ~ 2.7

![](/images/C++ Prime 5 & 2.5~2.7.png)

十进制：20 & 八进制：020 & 十六进制：0x20或者0X20

### 2.8

~~~C++
#include <iostream>
using namespace std;
int main()
{    
    cout << "2M" << '\n';
    cout << '2' << '\t' << 'M' << '\n';
    return 0;
}
~~~

### 2.9

先定义 & 3.14被强转为3 & wage未定义 & 同2

### 2.10

glo_str = "" & glo_int = 0 & loc_int 不确定 & loc_str = ""

### 2.11

定义 & 定义 & 声明

### 2.12

**字母+数字+下划线（必须以字母或者下划线开头）**

**C++中关于变量命名的规范：**

1. **能体现变量的实际意义**
2. **变量名一般采用小写字母**
3. **用户自定义类名一般以大写字母开头**
4. **多个单词定义的变量名应有区分Student_loan  而不是  Studentloan**

错，double 是关键字 & 对 & 不能带- & 不能数字开头 & 对

### 2.13

j = 100，因为在这个语句块内，局部变量 i(100) 生效，如果想用全局变量 i(42) ，可以使用 j = ::i;

### 2.14

i = 100, sum=45, for循环语句内的i只活在该语句内，而 std::cout 在main语句块内，自然是取得100

### 2.15

可以 & 不行，引用需绑定对象 & 可以 & 不行，引用必须初始化

### 2.16

隐式类型转换

### 2.17

10 10，等于给 i = 5 后 i = 10

### 2.18

~~~C++
int a = 1, b =2, *p = a;
*p = 10;//更改指针所指对象的指
p = &b;//更改指针的值
~~~

### 2.19

指针自己本身就是一个对象，指针之间可以相互赋值和拷贝，在其生命周期内还可指向不同的对象 & 引用在汇编代码中就是指针常量

指针无需在定义时初始化 & 引用必须初始化

指针需要解引用 & 引用不需要

### 2.20

42的平方

### 2.21

非法，类型不一 & 非法，无取地址符号 & 合法

### 2.22

如果指针不是空&如果指针指向的对象的值不是0

### 2.24

因为 long 与 int 类型不匹配，而 void 指针可以接收任意类型的指针

因为 void 指针只知道头地址，它并不需要该对象的长度

### 2.25 

int 指针 ip，int 变量 i，int 引用 r 绑定 i & int 变量 i，int 指针 p 为空 & ip 指针，ip2 变量

### 2.26

错，没有初始化 & 对 & 对 & ++sz 错误，常量不更改

### 2.27

错，引用需要绑定对象 & 如果 i2 不是 const 就对 & 同1 & 对 & 对 & 错，没有引用的 const，引用不是对象 & 对

### 2.28

指针常量需初始化 & 同1 & 常量 ic 需初始化 & 同1 & 对

### 2.29

对 & const int 和 int 不对等 & 同上 & 错，指针常量不能更改其值 & 同上 & 常量不能改变

### 2.30

顶层 & 底层 & 顶层 & 底层

### 2.31

对 & 错，底层 const & 对 & 同2 & 对

### 2.32

*p = nullptr;

### 2.33 & 2.34

对 & 对 & 对 & d 是整数指针 \*d 就行 & 错，解引用也不行，指向的是常量 & g 是引用，ci 是常量

### 2.35

int & const int 引用 & const int 指针 & const int & 同2

### 2.36 & 2.37

c int & d int 引用

### 2.38

decltype 处理顶层 const 和引用的方式与 auto 有些许不同。

decltype((var)) 的结果永远是引用。

如果使用的表达式是个变量，则 decltype 返回该变量的类型。

（包括顶层 const 和引用在内）

而 auto 会忽略顶层 const，以及直接识别引用绑定的对象。

~~~c++
int i = 0, &r = i;
// same
auto a = i;
decltype(i) b = i;
// different
auto c = r;
decltype(r) d = i;
~~~

### 2.39

~~~C++
D:\WorkSpace\C++\Test.cpp:5:2: 错误：结构定义后需要‘;’
 } int main()
  ^
  ;
~~~

## 第三章

### 3.1

头文件中不应使用using声明，以避免名字冲突

### 3.2

~~~C++
string s;
getline(cin,s);
while(cin >> s);
~~~

### 3.3

对于 string 类的输入函数，它会自动忽略开头的空白（空格、制表符、换行等等），从第一个真正的字符开始直到下一个空白。

对于 getline() 函数，它会保存字符串中的空白符，它读入数据，直到遇到换行符位置。

### 3.4

~~~C++
cin >> s1 >> s2;
cout << (s1 > s2 ? s1 : s2) << endl;
cout << (s1.size() > s2.size() ? s1 : s2) << endl;
~~~

### 3.5

~~~C++
cin >> s1 >> s2;
cout << s1 + s2;
cout << s1 + " " + s2 << endl; 
~~~

### 3.6

~~~C++
for(auto &c : s){
    C = 'X';
}
~~~

### 3.7

没有改变，因为变量只是 char 而不是 char 引用

### 3.8

~~~C++
while(i < s.size()){
    s[i++]='X';
}
for(int i = 0;i < s.size();i++){
    s[i++]='X';
}
~~~

范围for，写起来快

### 3.9

不合法，越界了，或许确实可以输出一个空格，但是不要这么做

### 3.10

~~~C++
cin >> s;
for(auto &c:s){
    if(!ispunct(c))cout << c;
}
~~~

### 3.11

const char&

### 3.12

vector的初始化：

1：引用不可以成为vector的元素，因为其不是对象。

2：可以用花括号初始化每一个值。

3：可以用括号指定元素个数或相同的元素值

对 & 不对，类型不一 & 对

### 3.13

0 & 10个0 & 10个42 & 10 & 10,42 & 10个“” & 10个“hi”

### 3.14 & 3.15

~~~C++
while(cin >> num) vec.push_back(num);
~~~

### 3.16

~~~C++
//我选择for循环
cout << s.size() << endl;
for(auto c:s){
    cout << c << endl;
}
~~~

### 3.17

~~~C++
while(cin >> s){
    vec.push_back(s);
}
for(auto c:s){
    for(auto ch:c){
        cout << toupper(ch);
    }
    cout << endl;
}
~~~

### 3.18

~~~C++
ivec.push_back(42);
~~~

### 3.19

~~~C++
vector<int> vec(10,42);//The best
vector<int> vec{42,..,42};
int a[]={42,...,42};
vector<int> vec(a,a+10);
~~~

### 3.20

~~~C++
for(int i=0;i<vec.size()-1;i++){
    cout << vec[i]+vec[i+1] << endl;
}
for(int i=0;i<vec.size()/2;i++){
    cout << vec[i]+vec[n-i-1] << endl;
}
~~~

### 3.21

~~~C++
//我选择for循环
cout << s.size() << endl;
for(auto c = s.cbegin();c != s.cend();c++){
    cout << *c << endl;
}
~~~

### 3.22

~~~C++
vector<string> text;
string s;
while(getline(cin,s)) text.push_back(s);
for(auto it = text.begin();it != text.end();it++){
    for(auto &c:*it) c=toupper(c);
    cout << *it <<endl;
}
~~~

### 3.23

~~~C++
vector<int> vec(10,2);
for(auto &c:vec){
    c<<=1;
    cout << c << " ";
}
~~~

### 3.24

~~~C++
for(auto i=vec.begin();i!=end()-1;i++){
    cout << *i+*(i+1) << endl;
}
for(auto i=vec.begin(),j=vec.end();i!=j;i++,j--){
    cout << *i + *j << endl;
}
~~~

### 3.25

~~~C++
for(auto c=vec.begin();c!=vec.end();c++){
    sc[*c/10]++;
}
~~~

### 3.26

因为vector迭代器并无加法运算符

### 3.27

对 & 对 & 如果txt_size()函数是constexpr修饰的就可 & 错，‘\0’放不下了

### 3.28

十个“” & 十个0 & 十个“” & 十个随机值

### 3.29

1. 数组初始化必须知道大小
2. vector内置函数支持
3. vector自动扩容

### 3.30

~~~C++
ix <= array_size //ix < array_size
~~~

### 3.31

~~~C++
int num[10];
for(int i=0;i<10;i++){
    num[i]=i;
}
~~~

### 3.32

~~~C++
vector<int> vec(num,num+10);
~~~

### 3.33

初始值未知，则最终的累加结果并无意义

### 3.34

相当于p1=p2

### 3.35

~~~C++
for(int *p=begin(num);p != end(num);p++)    *p=0;
~~~

### 3.36

~~~C++
for(int *p=begin(num1),*q=begin(num2);p != end(num1)&&q != end(num2);p++,q++)    if(*p!=*q)    return false;
for(auto p=num1.begin(),q=num2.end();p != num1.end()&&q != num2.end();p++,q++)    if(*p!=*q)    return false;
~~~

### 3.37

hello，按字节输出

### 3.38

两个地址相加得到的地址没什么实际意义，除非是目标地址就是这两个地址相加才能得到的，但这实在是没啥意义。

### 3.39

~~~C++
if(s1==s2);
auto ans = strcmp(s1,s2);
~~~

### 3.40

~~~C++
const char s1[] = "Hello";
const char s2[] = "world!";
 
size_t n = strlen(s1) + strlen(" ") + strlen(s2) + 1;
char* s3 = new char[n];
 
strcpy(s3, s1);
strcat(s3, " ");
strcat(s3, s2);
~~~

### 3.41

~~~C++
vector<int> vec(num,num+10);
~~~

### 3.42

~~~C++
for(int i=0;i<vec.size();i++)    num[i] = vec[i];
~~~

### 3.43

~~~C++
int ia[3][4] = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11};
// 用于管理迭代的范围
for (const int(&p)[4] : ia)
    for (int q : p) cout << q << " ";
cout << endl;

// 使用下标的普通for循环
for (size_t i = 0; i != 3; ++i)
    for (size_t j = 0; j != 4; ++j) cout << ia[i][j] << " ";
cout << endl;

// 使用指针
for (int(*p)[4] = ia; p != ia + 3; ++p)
    for (int* q = *p; q != *p + 4; ++q) cout << *q << " ";
~~~

### 3.44

~~~C++
// 使用类型别名
using int_array = int[4];

for (int_array& p : ia)
    for (int q : p) cout << q << " ";
cout << endl;

for (int_array* p = ia; p != ia + 3; ++p)
    for (int* q = *p; q != *p + 4; ++q) cout << *q << " ";
~~~

### 3.45

~~~C++
for (auto& p : ia)
    for (int q : p) cout << q << " ";
cout << endl;

for (auto* p = ia; p != ia + 3; ++p)
    for (int* q = *p; q != *p + 4; ++q) cout << *q << " ";
~~~

## 第四章

### 4.1

105

### 4.2

*(vec.begin()) & *(vec.begin())+1

### 4.3

可以，编写者自己用括号强制约定就行，可读性也强

### 4.4

((12 / 3) * 4) + (5 * 15) +((24 % 4) / 2) = 91

### 4.5

-86 & -18 & 0 & -2

### 4.6

~~~C++
if(num % 2 == 0);
if(num ^ 1 == 0);
~~~

### 4.7

~~~C++
short a = 32768;
unsigned a = -10;
int a = 123456789*123456789;
~~~

### 4.8

逻辑与：左面为真再判断右面

逻辑或：先判断左面为假再判断右面

相等性运算符：右边的转换为左边的类型再与左边比较

### 4.9

先看cp是否是空指针，随后看cp所指向的地方是否为空

### 4.10

~~~C++
while(cin >> num && num != 42);
~~~

### 4.11

~~~C++
if(a>b?(b>c?(c>d?true:false):false):false);
~~~

### 4.12

判断i是否为相应时刻(j<k)的0或者1

### 4.13

3.0 & 3 & 3 & 3.5

### 4.14

右值不可放在表达式左侧 & 恒为true

### 4.15

非法，得先让pi指向某个int类型的左值，然后把表达式改为dval = ival = *pi = 0即可。

### 4.16

!=优先级高于=，(p = getPtr()) != 0 & 恒为true，if(i == 1024)

### 4.17

前置返回i+1，后置返回i然后再+1

### 4.18

第一个没有输出，并且还会输出v.end()

### 4.19

指针不为空且指针里不为空并往下一步走 & 后两个改成ival+1

### 4.20

解引用后迭代器+1 & 迭代器里的是string无法自增 & 不合法，iter无法使用点运算符 & iter指向的是否为空 & string无自增 & iter指向是否为空，然后迭代器加一

### 4.21

~~~C++
for(auto &c:vec)    c % 2 ? c *= 2 : c;
~~~

### 4.22

~~~C++
//只用条件运算符
string Sscore = score < 60 ? "fail" : (score < 75 ? "low pass" : (score < 90 ? "pass" : "high pass"));

//用if语句
if(score<60)    Sscore = "fail";
else if(score<75)    Sscore = "low pass";
else if(score<90)    Sscore = "pass";
else    Sscore = "high pass";
~~~

### 4.23

~~~C++
string s = "word";
string p1 = s + (s[s.size() - 1] == 's' ? "" : "s");
~~~

### 4.24 

Since we are nesting conditional operations, we are essentially grouping expressions with each others using operators of equal precedence, i.e., two ?: operators. Here, the rules of associativity dictates how the expressions of these operators are grouped together and eventually evaluated. Right associativity means that they will be grouped from right to left as such:

```c++
finalgrade = (grade > 90) ? "high pass" : ((grade < 60) ? "fail" : "pass");
```

Note how this grouping means that outer conditional operation will not be evaluated until the inner one is evaluated first, if the grade is less than or equal to 90.

If the operator were left associative we would have the following grouping instead:

```c++
finalgrade = ((grade > 90) ? "high pass" : (grade < 60)) ? "fail" : "pass";
```

This would result in a compile error because the outer conditional operator would have incompatible operand types: const char * and bool.

### 4.25

-7296

### 4.26

The C++ standard does not specify the size of integral types in bytes, but it specifies minimum ranges they must be able to hold. The minimum range of `unsigned int` is 0 to 65535. Since some implementations use only the minimum 16 bits for `unsigned int`, this could cause undefined behavior.

### 4.27

~~~C++
unsigned long ull = 3, ul2 = 7;// 0101 0111
0101 & 0111 & true & false
~~~

### 4.28

~~~C++
    // by using method below only include what is needed.
    using std::cout;
    using std::endl;
    
    // void type
    cout << "void: nullptr_t\t" << sizeof(std::nullptr_t) << " bytes" << endl << endl;
    
    // boolean type
    cout << "bool:\t\t" << sizeof(bool) << " bytes" << endl << endl;
    
    // charactor type
    cout << "char:\t\t" << sizeof(char) << " bytes" << endl;
    cout << "wchar_t:\t" << sizeof(wchar_t) << " bytes" << endl;
    cout << "char16_t:\t" << sizeof(char16_t) << " bytes" << endl;
    cout << "char32_t:\t" << sizeof(char32_t) << " bytes" << endl << endl;
    
    // integers type
    cout << "short:\t\t" << sizeof(short) << " bytes" << endl;
    cout << "int:\t\t" << sizeof(int) << " bytes" << endl;
    cout << "long:\t\t" << sizeof(long) << " bytes" << endl;
    cout << "long long:\t" << sizeof(long long) << " bytes" << endl << endl;
    
    // floating point type
    cout << "float:\t\t" << sizeof(float) << " bytes" << endl;
    cout << "double:\t\t" << sizeof(double) << " bytes" << endl;
    cout << "long double:\t" << sizeof(long double) << " bytes" << endl << endl;
	
    // Fixed width integers
    cout << "int8_t:\t\t" << sizeof(int8_t) << " bytes" << endl;
    cout << "uint8_t:\t" << sizeof(uint8_t) << " bytes" << endl;
    cout << "int16_t:\t" << sizeof(int16_t) << " bytes" << endl;
    cout << "uint16_t:\t" << sizeof(uint16_t) << " bytes" << endl;
    cout << "int32_t:\t" << sizeof(int32_t) << " bytes" << endl;
    cout << "uint32_t:\t" << sizeof(uint32_t) << " bytes" << endl;
    cout << "int64_t:\t" << sizeof(int64_t) << " bytes" << endl;
    cout << "uint64_t:\t" << sizeof(uint64_t) << " bytes" << endl;
~~~

### 4.29

~~~C++
int x[10];   int *p = x;
cout << sizeof(x)/sizeof(*x) << endl;//10
cout << sizeof(p)/sizeof(*p) << endl;//1
~~~

### 4.30

~~~C++
sizeof x + y      // (sizeof x)+y . "sizeof" has higher precedence than binary `+`.
sizeof p->mem[i]  // sizeof(p->mem[i])
sizeof a < b      // sizeof(a) < b
sizeof f()        //If `f()` returns `void`, this statement is undefined, otherwise it returns the size of return type.
~~~

### 4.31

Advice: Use Postfix Operators only When Necessary

Readers from a C background might be surprised that we use the prefix increment in the programs we've written. The reason is simple: The prefix version avoids unnecessary work. It increments the value and returns the incremented version.The postfix operator must store the original value so that it can return the unincremented value as its result. If we don’t need the unincremented value, there’s no need for the extra work done by the postfix operator.

For ints and pointers, the compiler can optimize away this extra work. For more complicated iterator types, this extra work potentially might be more costly. By habitually using the prefix versions, we do not have to worry about whether the performance difference matters. Moreover—and perhaps more importantly—we can express the intent of our programs more directly.

### 4.32

~~~C++
constexpr int size = 5;
int ia[size] = { 1, 2, 3, 4, 5 };
for (int *ptr = ia, ix = 0;
    ix != size && ptr != ia+size;
    ++ix, ++ptr) { /* ... */ }
//ptr is a point, but ix is a int var
~~~

### 4.33

~~~C++
someValue ? ++x, ++y : --x, --y
//which is same as (someValue ? ++x, ++y : --x), --y
~~~

### 4.34

~~~C++
if (fval);// float converted to bool
dval = fval + ival;// int converter to float, then the result converted to double
dval + ival * cval;// char converted to int, then the result converter to double
~~~

### 4.35

~~~C++
cval = 'a' + 3;// char converted to int, then the result(int) converted to char
fval = ui - ival * 1.0;// int converted to double, the ui converted to double, the result converted to float
dval = ui * fval;// ui converted to float, then the result converted to double
cval = ival + fval + dval;// ival converted to float, float converted to double, double converted to char
~~~

### 4.36

~~~C++
i*=static_cast<int> d;
~~~

### 4.37

~~~C++
int i;double d;const string *ps;char *pc;void *pv;
pv = (void*)ps;// pv = static_cast<void*>(const_cast<string*> ps);
i = int(*pc);// i = static_cast<int>(*pc);
pv = &d;// pv = static_cast<void*>(&d);
pc = (char*) pv;// pc = static_cast<char*>(pv);
~~~

### 4.38

~~~C++
double slope = static_cast<double>(j/i);//the result of (j/i) converted to double and assigned to slope
~~~

## 第五章

### 5.1

To be used as spaceholder

### 5.2

块是用花括号括起来的（可能为空的）语句和声明的序列 & 如果在程序的某个地方，语法上需要一条语句，但是逻辑上需要多条语句，那就用块

### 5.3

~~~C++
while(val <= 10)
    sum+=val,++val;
~~~

### 5.4

~~~C++
string::iterator iter;
while(iter != s.end()){}

bool status;
while(status = find(word)){}
if(!status){}
~~~

### 5.5

~~~c++
vector<int> stu{50, 60, 20, 100};
vector<string> sc{"F", "E", "D", "C", "B", "A"};
for (auto c : stu)
{
    if (c < 60)
        cout << sc[0] << endl;
    cout << sc[(c - 50) / 10] << endl;
}
~~~

### 5.6

~~~C++
c < 60 ? sc[0] : sc[(c-50)/10];
~~~

### 5.7

~~~C++
if(ival1 != ival2)
    ival1 = ival2;// add a ';'
else ival1 = ival2 = 0;

if(ival < minval){
    minval = ival;
    occurs = 1;
}

int ival;
if(ival=get_value())
    cout << "ival= " << ival << endl;
else cout << "ival = 0\n";

if(ival = 0)
    ival = get_value();
~~~

### 5.8

if 比 else 多的时候， else 会与最近的 if 配套

### 5.9

~~~C++
unsigned aCnt = 0, eCnt = 0, iCnt = 0, oCnt = 0, uCnt = 0;
char ch;
while (cin >> ch)
{
    if (ch == 'a') ++aCnt;
    else if (ch == 'e') ++eCnt;
    else if (ch == 'i') ++iCnt;
    else if (ch == 'o') ++oCnt;
    else if (ch == 'u') ++uCnt;
}
~~~

### 5.10

~~~C++
while (cin >> ch)
    switch (ch)
    {
        case 'a':
        case 'A':
            ++aCnt;
            break;
        case 'e':
        case 'E':
            ++eCnt;
            break;
        case 'i':
        case 'I':
            ++iCnt;
            break;
        case 'o':
        case 'O':
            ++oCnt;
            break;
        case 'u':
        case 'U':
            ++uCnt;
            break;
    }
~~~

### 5.11

~~~C++
while (cin >> std::noskipws >> ch)// noskipws, 不忽略任意地方的空格
    switch (ch)
    {
        case 'a':
        case 'A':
            ++aCnt;
            break;
        case 'e':
        case 'E':
            ++eCnt;
            break;
        case 'i':
        case 'I':
            ++iCnt;
            break;
        case 'o':
        case 'O':
            ++oCnt;
            break;
        case 'u':
        case 'U':
            ++uCnt;
            break;
        case ' ':
            ++spaceCnt;
            break;
        case '\t':
            ++tabCnt;
            break;
        case '\n':
            ++newLineCnt;
            break;
    }
~~~

### 5.12

~~~C++
 while (cin >> std::noskipws >> ch)
 {
     switch (ch)
     {
         case 'a':
         case 'A':
             ++aCnt;
             break;
         case 'e':
         case 'E':
             ++eCnt;
             break;
         case 'i':
             if (prech == 'f') ++fiCnt;
         case 'I':
             ++iCnt;
             break;
         case 'o':
         case 'O':
             ++oCnt;
             break;
         case 'u':
         case 'U':
             ++uCnt;
             break;
         case ' ':
             ++spaceCnt;
             break;
         case '\t':
             ++tabCnt;
             break;
         case '\n':
             ++newLineCnt;
             break;
         case 'f':
             if (prech == 'f') ++ffCnt;
             break;
         case 'l':
             if (prech == 'f') ++flCnt;
             break;
     }
     prech = ch;
 }
~~~

### 5.13

~~~C++
unsigned aCnt = 0, eCnt = 0, iouCnt = 0;
char ch = next_text();
switch (ch) {
    case 'a': aCnt++;// break;
    case 'e': eCnt++;// break;
    default: iouCnt++;// break;
}

unsigned index = some_value();
int ix;// add a statement
switch (index) {
    case 1:
        ix = get_value();
        ivec[ ix ] = index;
        break;
    default:
        ix = ivec.size()-1;
        ivec[ ix ] = index;
}

unsigned evenCnt = 0, oddCnt = 0;
int digit = get_num() % 10;
switch (digit) {
    case 1, 3, 5, 7, 9:
        oddcnt++;// oddCnt
        break;
    case 2, 4, 6, 8, 10:
        evencnt++;// evenCnt
        break;
}

const unsigned ival=512, jval=1024, kval=4096;
// case label must be a constant expression
unsigned bufsize;
unsigned swt = get_bufCnt();
switch(swt) {
    case ival:
        bufsize = ival * sizeof(int);
        break;
    case jval:
        bufsize = jval * sizeof(int);
        break;
    case kval:
        bufsize = kval * sizeof(int);
        break;
}
~~~

### 5.14

~~~C++
pair<string, int> max_duplicated;
int count = 0;
for (string str, prestr; cin >> str; prestr = str)
{
    if (str == prestr)
        ++count;
    else
        count = 0;
    if (count > max_duplicated.second)
        max_duplicated = {prestr, count};
}
if (max_duplicated.first.empty())
    cout << "There's no duplicated string." << endl;
else
    cout << "the word " << max_duplicated.first << " occurred " << max_duplicated.second + 1 << " times. " << endl;
~~~

### 5.15

~~~C++
int ix;
for(ix = 0; ix != sz; ++ix){}
if(ix != sz);

int ix;
for(; ix != sz; ++ix){}

for(int ix = 0; ix != sz; ++ix){}
~~~

### 5.16

~~~C++
// while
int i;
while (cin >> i);

// same as for
for (int i = 0; cin >> i;);

// for
for (int i = 0; i != size; ++i);

// same as while
int i = 0;
while (i != size)
    ++i;

//用for循环更舒服一些，毕竟可以规定局部变量的生命期，虽然可读性会差一些。
~~~

### 5.17

~~~C++
bool is_pre(vector<int> &l, vector<int> &r){
    if(l.size()>r.size())
        return is_pre(r,l);
    for(int i=0;i<l.size();i++){
        if(l[i]!=r[i])
            return false;
    }
    return true;
}
int main(){
    vector<int> l{0,1,1,2};
    vector<int> r{0,1,1,2,3,5,8};
    cout << (is_pre(l,r) ? "Yes" : "No");
    return 0;
}
~~~

### 5.18

~~~c++
do{
    int v1, v2;
    cout << "Please enter two numbers to sum:";
    if(cin >> v1 >> v2)
        cout << "Sum is: " << v1 + v2 << endl;
}while(cin);

do{
    //..
}while(ival = get_response());

int ival = get_response();
do{
    ival = get_response();
}while(ival);// while(ival)中的ival和do{}中的ival不在一个作用域中
~~~

### 5.19

~~~C++
string s1,s2;
do{
    cout << "Please input two string:\n";
    cin >> s1 >> s2;
    cout << (s1.size() > s2.size() ? s2 : s1) << endl;
    cout << "Do you wanna continue?(yes or no)\n";
    cin >> s1;
}while(!s1.empty() && tolower(s1[0]=='y'));
~~~

### 5.20

~~~C++
string re,t;
while(cin >> re)
    if(re == t)
        break;
    else
        t=re;
if(cin.eof())
    cout << "No repeated" << endl;
else 
    cout << re << endl;
~~~

### 5.21

~~~C++
string curr, prev;
bool no_twice = true;
while (cin >> curr) 
{
    if (isupper(curr[0]) && prev == curr)
    {
        cout << curr << endl;
        no_twice = false;
        break;
    }
    prev = curr;
}
if (no_twice)
    cout << "no word was repeated." << endl;
~~~

### 5.22

~~~C++
for(int sz = get_size(); sz <= 0; sz = get_size());
~~~

### 5.23 ~ 5.25

~~~C++
cin >> i >> j;
cout << i / j <<endl;

if (j == 0)// 5.24
    throw runtime_error("divisor is 0");
cout << i / j << endl;

for (int i, j; cout << "Input two integers:\n", cin >> i >> j; )// 5.25
{
    try 
    {
        if (j == 0) 
            throw runtime_error("divisor is 0");
        cout << i / j << endl;
    }
    catch (runtime_error err) 
    {
        cout << err.what() << "\nTry again? Enter y or n" << endl;
        char c;
        cin >> c;
        if (!cin || c == 'n')
            break;
    }
}
~~~

## 第六章

### 6.1

形参:在函数参数表中声明的局部变量，它们由函数调用中提供的实参初始化

实参:函数调用中提供的用于初始化函数形参的值

### 6.2

~~~C++
int f(){// string f()
    string s;
    // ..
    return s;// string != int
}

void f2(int i){}

int calc(int v1,int v2){}

double square(double x){
    return x * x;
}
~~~

### 6.3

~~~C++
int fact(int i){
    if(i < 0){
        runtime_error err("Input cannot be a negative number");
        cout << err.what() << endl;
    }
    return i > 1 ? i * fact(i-1) : i;
}
~~~

### 6.4

~~~C++
int main(){
    int n;
    cout << "Please input a number\n";
    cin >> n;
    cout << fact(n) << endl;
    return 0;
}
~~~

### 6.5

~~~C++
int myAbs(int i){
    if(i < 0)
        return -i;
    return i;
}
~~~

### 6.6

~~~C++
size_t count_add(int n)
{
    static size_t ctr = 0;
    ctr += n;
    return ctr;
}
int main()
{
    for (size_t i = 0; i != 10; ++i)
        cout << count_add(i) << endl;
    return 0;
}
~~~

### 6.7

~~~C++
size_t count_add(int n)
{
    static size_t ctr = 0;
    return ctr++;
}
~~~

### 6.8

~~~C++
// Chapter6.h
#pragma once
int fact(int val);
int func();
template <typename T> 
T abs(T i)
{
    return i >= 0 ? i : -i;
}
~~~

### 6.9

~~~C++
//fact.cc
#include "Chapter6.h"
#include <iostream>
int fact(int val)
{
    if (val == 0 || val == 1) return 1;
    else return val * fact(val-1);
}

int func()
{
    int n, ret = 1;
    std::cout << "input a number: ";
    std::cin >> n;
    while (n > 1) ret *= n--;
    return ret;
}

//factMain.cc
#include "Chapter6.h"
#include <iostream>
int main()
{
    std::cout << "5! is " << fact(5) << std::endl; 
    std::cout << func() << std::endl; 
    std::cout << abs(-9.78) << std::endl;
    return 0;
}
~~~

### 6.10

~~~C++
void swap(int *p,int *q){
    int t = *p;
    *p = *q;
    *q = t;
}
int main(){
    int i,j;
    cin >> i >> j;
    swap(&i,&j);
    cout << i << j;
    return 0;
}
~~~

### 6.11

~~~C++
void reset(int &i){
    i = 0;
}
int main(){
    int i = 1;
    reset(i);
    cout << i << endl;
    return 0;
}
~~~

### 6.12

~~~C++
void swap(int &l,int &r){
    int t = l;
    l = r;
    r = t;
}
// 引用不用解引用，也不用拷贝
~~~

### 6.13

~~~C++
void f(T);// 只传值，不影响实参
void f(&T); // 影响实参
~~~

### 6.14

~~~C++
void reset(int &i)
{
    i = 0;
}

void print(std::vector<int>::iterator begin, std::vector<int>::iterator end)
{
    for (std::vector<int>::iterator iter = begin; iter != end; ++iter)
        std::cout << *iter << std::endl;
}
~~~

### 6.15

函数不修改 s 的值，但是 occurs 的值是会变化的 & 因为 c 可能是个临时变量 & 那 s 就可能被改变 & 无法改变 occurs 的值，occurs = 0 就会报错

### 6.16

~~~C++
bool is_empty(const string& s){
    return s.empty();
}
~~~

### 6.17

~~~C++
bool hav_up(const string& s){
    for(auto c:s){
        if(isupper(c))return true;
    }
    return false;
}

void toUpperString(string& s){
    for(auto& c:s){
        c = toupper(c);
    }
}
~~~

### 6.18

~~~C++
bool compare(matrix &a,matrix &b);

vector<int>::iterator change_val(int a,vector<int>::iterator b);
~~~

### 6.19

~~~C++
double calc(double);
int count(const string &,char);
int sum(vector<int>::iterator,vector<int>::iterator,int);
vector<int> vec(10);

calc(23.4,55.1);// 多了个参数
count("abcda",'a');
calc(66);
sum(vec.begin(),vec.end(),3.8);
~~~

### 6.20

If we can use `const`, just use it. If we make a parameter a plain reference when it could be a reference to `const`, the reference value maybe changed.

### 6.21

~~~C++
int com(int a,const int *const b){
    return a > *b ? a : *b;
}
~~~

### 6.22

~~~C++
void swap(int*& p,int*& q){
	auto t = p;
    p = q;
    q = t;
}
~~~

### 6.23

~~~C++
void print(const int* p){
    if(p)
        cout << *p << endl;
}
void print(const char* p){
    if(p)
        while(*p)
            cout << *p++;
    cout << endl;
}
void print(const int* beg,const int* end){
    while(beg != end)
        cout << *beg++ <<endl;
}
void print(const int a[],size_t size){
    for(size_t i = 0;i < size;i++)
        cout << a[i] << endl;
}
void print(int (&arr)[2]){
    for(auto i:arr)
        cout << i << endl;
}
int main(){
    int i = 0, j[2] = {0, 1};
    char ch[5] = "test";
    print(&i);
    print(ch);
    print(begin(j),end(j));
    print(j,end(j)-begin(j));
    print(j);
    return 0;
}
~~~

### 6.24

~~~C++
void print(const int (&a)[10]){
    for(size_t i = 0;i != 10;++i)
        cout << a[i] << endl;
}
~~~

### 6.25 & 6.26

~~~C++
#include <iostream>
#include <string>

int main(int argc, char **argv)
{
    std::string str;
    for (int i = 1; i != argc; ++i)
        str += std::string(argv[i]) + " ";

    std::cout << str << std::endl;
    return 0;
}
~~~

### 6.27

~~~C++
#include<iostream>
#include<initialzer_list>
using namespace std;
int sum(initialzer_list<int> const& il){
    int sum = 0;
    for(auto i:il)
        sum += i;
    return sum;
}
int main(){
    auto il = {1,2,3,4,5,6,7,8,9};
    cout << sum(il) << endl;
    return 0;
}
~~~

### 6.28

`const string&`

### 6.29

Depends on the type of elements of `initializer_list`. When the type is [PODType](http://en.cppreference.com/w/cpp/concept/PODType), reference is unnecessary. Because `POD` is **cheap to copy** (such as `int`). Otherwise, Using reference(`const`) is the better choice.

### 6.30

~~~C++
bool str_subrange(const string &str1, const string &str2){
    if(str1.size() == str2.size())
        return str1 == str2;
    auto size = (str1.size() < str2.size()) ? str1.size() : str2.size();
    for(decltype(size) i = 0; i != size; ++i){
        if(str1[i] != str2[i])
            return;
    }
}
/*
D:\WorkSpace\C++\Test.cpp: 在函数‘bool str_subrange(const string&, const string&)’中:
D:\WorkSpace\C++\Test.cpp:38:13: 错误：在返回‘bool’的函数中，返回语句不带返回值 [-fpermissive]
             return;
             ^~~~~~
*/
~~~

### 6.31

It is valid to return a reference when the reference does not refer to a local object. The Same applies for a reference to const, but only when the returned value is not expected to be an lvalue.

### 6.32

~~~C++
int &get(int *arry, int index){return arry[index];}
int main(){
    int ia[10];
    for(int i = 0; i != 10; ++i)
        get(ia, i) = i;
    return 0;
}
// legal, it gave the values (0 ~ 9) to array ia.
~~~

### 6.33

~~~C++
using Iter = vector<int>::const_iterator;
void print(Iter first, Iter last)
{
    if (first != last)
    {
        cout << *first << " ";
        print(++first, last);
    }
}
~~~

### 6.34

When the recursion termination condition becomes `var != 0`, two situations can happen :

- case 1 : If the argument is positive, recursion stops at 0.(Note : There is one extra multiplication step though as the combined expression for factorial(5) reads 5 * 4 * 3 * 2 * 1 * 1. In terms of programming languages learning, such subtle difference probably looks quite trivial. In algorithms analysis and proof, however, this extra step may be super important.)
- case 2 : if the argument is negative, recursion would never stop. As a result, a stack overflow would occur.

### 6.35

`val--` 的值是 `val` , 陷入死循环

### 6.36 & 6.37

~~~c++
string (&fun(string (&arr)[10]))[10];

typedef string[10] strarr;
using strarr = string[10];
strarr &fun(strarr& arr);

auto fun(strarr& arr) -> string(&)[10];

string[10] sarr;
decltype(sarr) &fun(strarr& arr);
~~~

### 6.38

~~~C++
int odd[] = {1,3,5,7,9};
int even[] = {0,2,4,6,8};
decltype(odd) &arrPtr(int i){
    return (i % 2) ? &odd : &even;
}
~~~

### 6.39

~~~C++
// 顶层const会被忽略，重复声明不会报错
int calc(int, int);
int calc(const int, const int);

// 返回值类型不影响重载，报错
int get();
double get();

// 可以
int *reset(int *);
double *reset(double *);
~~~

### 6.40

~~~C++
int ff(int a, int b = 0, int c = 0);
char *init(int ht = 24,int wd, char bckgrnd);// wd, bckgrnd都需要初始化
~~~

### 6.41

~~~C++
char *init(int ht, int wd = 80, char bckgrnd = ' ');
init();// 错误
init(24,10);// 正确
init(14,'*');// 对，但是 wd 会变成 * 的 ASCII 值
~~~

### 6.42

~~~C++
string make_plural(size_t ctr, const string &word, const string &ending = "s"){
    return (ctr > 1) ? word + ending : word;
}
int main()
{
    cout << "singual: " << make_plural(1, "success", "es") << " "
         << make_plural(1, "failure") << endl;
    cout << "plural : " << make_plural(2, "success", "es") << " "
         << make_plural(2, "failure") << endl;
    return 0;
}
~~~

### 6.43

Both two should put in a header. (a) is an inline function. (b) is the declaration of useful function. we always put them in the header.

### 6.44

~~~C++
inline bool is_shorter(const string &lft, const string &rht)
{
    return lft.size() < rht.size();
}
~~~

### 6.45

For example, the function `arrPtr` in Exercise 6.38 and `make_plural` in Exercise 6.42 should be defined as `inline`. But the function `func` in Exercise 6.4 shouldn't. It is not that small and it's only being called once. Hence, it will probably not expand as inline.

### 6.46 (Two explanations)

No. Because `std::string::size()` is not a `constexpr` function and `s1.size() == s2.size()` is not a constant expression.

> **For a** non-template, non-defaulted **constexpr function** or a non-template, non-defaulted, non-inheriting constexpr constructor, **if no argument values exist such that an invocation of the function or constructor could be an evaluated subexpression of a core constant expression (5.19), the program is ill-formed;** no diagnostic required. (N3690 §7.1.5 [dcl.constexpr]/5)



显然 `isShorter` 函数不符合 `constexpr` 函数的要求，它虽然只有一条 `return` 语句，但是返回的结果调用了标准库 `string` 类的 `size()` 函数和 `<` 比较符，无法构成常量表达式，因此不能改写成 `constexpr` 函数。

> constexpr 函数是指能用于常量表达式的函数，constexpr函数的返回类型和所有形参的类型都得是字面值类型，而且函数体中必须有且只有一条 return语句。 

### 6.47

~~~C++
void printVec(vector<int> &vec)
{
#ifndef NDEBUG
    cout << "vector size: " << vec.size() << endl;
#endif
    if (!vec.empty())
    {
        auto tmp = vec.back();
        vec.pop_back();
        printVec(vec);
        cout << tmp << " ";
    }
}
int main()
{
    vector<int> vec{ 1, 2, 3, 4, 5, 6, 7, 8, 9 };
    printVec(vec);
    cout << endl;
    return 0;
}
~~~

### 6.48

~~~C++
string s;
while(cin >> s && s != sought){}
assert(s == sought);// 从输入开始, cin 里一直都是有值的, 所以没啥意义
~~~

### 6.49

candidate function:

> Set of functions that are considered when resolving a function call. (all the functions with the name used in the call for which a declaration is in scope at the time of the call.)

viable function:

> Subset of the candidate functions that could match a given call. It have the same number of parameters as arguments to the call, and each argument type can be converted to the corresponding parameter type.

### 6.50

~~~C++
f(2.56, 42);// illegal. 2.56 match the double, but 42 match the int.
f(42);// match void f(int).
f(42, 0);// match void f(int, int).
f(2.56, 3.14);// match void f(double, double = 3.14).
~~~

### 6.51

~~~C++
void f()
{
    cout << "f()" << endl;
}
void f(int)
{
    cout << "f(int)" << endl;
}
void f(int, int)
{
    cout << "f(int, int)" << endl;
}
void f(double, double)
{
    cout << "f(double, double)" << endl;
}
int main()
{
    //f(2.56, 42); // error: 'f' is ambiguous.
    f(42);
    f(42, 0);
    f(2.56, 3.14);   
    return 0;
}
~~~

### 6.52

~~~C++
void manip(int, int);
manip('a', 'z');// Match through a promotion
manip(55.4, dobj);// Arithmetic type conversion
~~~

### 6.53

~~~C++
int calc(int&, int&);// calls lookup(int&)
int calc(const int&, const int&);// calls lookup(const int&)

int calc(char*, char*);// calls lookup(char*)
int calc(const char*, const char*);// calls lookup(const char*)

int calc(char*, char*);// illegal. both calls lookup(char*)
int calc(char* const, char* const);
~~~

### 6.54

~~~C++
int func(int a, int b);

using pFunc1 = decltype(func) *;
typedef decltype(func) *pFunc2;
using pFunc3 = int (*)(int a, int b);
using pFunc4 = int(int a, int b);
typedef int(*pFunc5)(int a, int b);
using pFunc6 = decltype(func);

std::vector<pFunc1> vec1;
std::vector<pFunc2> vec2;
std::vector<pFunc3> vec3;
std::vector<pFunc4*> vec4;
std::vector<pFunc5> vec5;
std::vector<pFunc6*> vec6;
~~~

### 6.55

~~~C++
int add(int a, int b) { return a + b; }
int subtract(int a, int b) { return a - b; }
int multiply(int a, int b) { return a * b; }
int divide(int a, int b) { return b != 0 ? a / b : 0; }
~~~

### 6.56

~~~C++
std::vector<decltype(func) *> vec{ add, subtract, multiply, divide };
for (auto f : vec)
    std::cout << f(2, 2) << std::endl;
~~~

## 第七章

### 7.1

~~~C++
struct Sales_data
{
    string bookNo;
    unsigned units_sold = 0;
    double revenue = 0.0;
};
int main()
{
    Sales_data total;
    if (cin >> total.bookNo >> total.units_sold >> total.revenue)
    {
        Sales_data trans;
        while (cin >> trans.bookNo >> trans.units_sold >> trans.revenue) 
        {
            if (total.bookNo == trans.bookNo) 
            {
                total.units_sold += trans.units_sold;
                total.revenue += trans.revenue;
            }
            else
            {
                cout << total.bookNo << " " << total.units_sold << " " << total.revenue << endl;
                total = trans;
            }
        }
        cout << total.bookNo << " " << total.units_sold << " " << total.revenue << endl;
    }
    else
    {
        std::cerr << "No data?!" << std::endl;
        return -1;
    }
    return 0;
}
~~~

### 7.2

~~~C++
struct Sales_data
{
    string isbn(){return bookNo;}
    Sales_data& combine(const Sales_data &rhs);
    string bookNo;
    unsigned units_sold = 0;
    double revenue = 0.0;
};

Sales_data& Sales_data::combine(const Sales_data &rhs){
    units_sold += rhs.units_sold;
    revenue += rhs.revenue;
    return *this;
}
~~~

### 7.3

~~~C++
int main()
{
    Sales_data total;
    if (cin >> total.bookNo >> total.units_sold >> total.revenue)
    {
        Sales_data trans;
        while (cin >> trans.bookNo >> trans.units_sold >> trans.revenue) 
        {
            if (total.isbn() == trans.isbn()) 
            {
                total.combine(trans);
            }
            else
            {
                cout << total.bookNo << " " << total.units_sold << " " << total.revenue << endl;
                total = trans;
            }
        }
        cout << total.bookNo << " " << total.units_sold << " " << total.revenue << endl;
    }
    else
    {
        std::cerr << "No data?!" << std::endl;
        return -1;
    }
    return 0;
}
~~~

### 7.4

~~~C++
class Person{
    string name;
    string address;
};
~~~

### 7.5

~~~C++
class Person{
    string name;
    string address;
public:
    auto getName(){return name;}
    auto getAddress(){return address;}
};
~~~

### 7.6

~~~C++
struct Sales_data {
    std::string const& isbn() const { return bookNo; };
    Sales_data& combine(const Sales_data&);

    std::string bookNo;
    unsigned units_sold = 0;
    double revenue = 0.0;
};

// member functions.
Sales_data& Sales_data::combine(const Sales_data& rhs)
{
    units_sold += rhs.units_sold;
    revenue += rhs.revenue;
    return *this;
}

// nonmember functions
std::istream &read(std::istream &is, Sales_data &item)
{
    double price = 0;
    is >> item.bookNo >> item.units_sold >> price;
    item.revenue = price * item.units_sold;
    return is;
}

std::ostream &print(std::ostream &os, const Sales_data &item)
{
    os << item.isbn() << " " << item.units_sold << " " << item.revenue;
    return os;
}

Sales_data add(const Sales_data &lhs, const Sales_data &rhs)
{
    Sales_data sum = lhs;
    sum.combine(rhs);
    return sum;
}
~~~

### 7.7

~~~C++
int main()
{
    Sales_data total;
    if (read(std::cin, total))
    {
        Sales_data trans;
        while (read(std::cin, trans)) {
            if (total.isbn() == trans.isbn())
                total.combine(trans);
            else {
                print(std::cout, total) << std::endl;
                total = trans;
            }
        }
        print(std::cout, total) << std::endl;
    }
    else
    {
        std::cerr << "No data?!" << std::endl;
        return -1;
    }
    return 0;
}
~~~

### 7.8

Define `read`'s Sales_data parameter as plain reference since it's intended to change the `revenue`'s value.

Define `print`'s Sales_data parameter as a reference to const since it isn't intended to change any member's value of this object.

### 7.9

~~~C++
class Person{
    string name;
    string address;
public:
    auto getName(){return name;}
    auto getAddress(){return address;}
};
istream& read(istream& is, Person& a){
    is >> a.name >> a.address;
    return is;
}
ostream& print(ostream& os, Person& a){
    os << a.name << " " << a.address;
    return os;
}
~~~

### 7.10

```c++
if(read(read(cin, data1), data2))
```

we can try to divide it like that:

```c++
std::istream &firstStep = read(cin, data1);
sdt::istream &secondStep = read(firstStep, data2);
if (secondStep)
```

the condition of the `if` statement would read two Sales_data object at one time.

### 7.11

~~~C++
//  ex7_11.h
//  Exercise 7.11

#ifndef CP5_ex7_11_h
#define CP5_ex7_11_h

#include <string>
#include <iostream>

struct Sales_data {
    Sales_data() = default;
    Sales_data(const std::string &s):bookNo(s) { }
    Sales_data(const std::string &s, unsigned n, double p):bookNo(s), units_sold(n), revenue(n*p){ }
    Sales_data(std::istream &is);
    
    std::string isbn() const { return bookNo; };
    Sales_data& combine(const Sales_data&);
    
    std::string bookNo;
    unsigned units_sold = 0;
    double revenue = 0.0;
};

// nonmember functions
std::istream &read(std::istream &is, Sales_data &item)
{
    double price = 0;
    is >> item.bookNo >> item.units_sold >> price;
    item.revenue = price * item.units_sold;
    return is;
}

std::ostream &print(std::ostream &os, const Sales_data &item)
{
    os << item.isbn() << " " << item.units_sold << " " << item.revenue;
    return os;
}

Sales_data add(const Sales_data &lhs, const Sales_data &rhs)
{
    Sales_data sum = lhs;
    sum.combine(rhs);
    return sum;
}

// member functions.
Sales_data::Sales_data(std::istream &is)
{
    read(is, *this);
}

Sales_data& Sales_data::combine(const Sales_data& rhs)
{
    units_sold += rhs.units_sold;
    revenue += rhs.revenue;
    return *this;
}

#endif

//  ex7_11.cpp
//  Exercise 7.11

#include "ex7_11.h"

int main()
{
    Sales_data item1;
    print(std::cout, item1) << std::endl;
    
    Sales_data item2("0-201-78345-X");
    print(std::cout, item2) << std::endl;
    
    Sales_data item3("0-201-78345-X", 3, 20.00);
    print(std::cout, item3) << std::endl;
    
    Sales_data item4(std::cin);
    print(std::cout, item4) << std::endl;
    
    return 0;
}
~~~

### 7.12

~~~C++
struct Sales_data;
std::istream &read(std::istream&, Sales_data&);

struct Sales_data {
    Sales_data() = default;
    Sales_data(const std::string &s):bookNo(s) { }
    Sales_data(const std::string &s, unsigned n, double p):bookNo(s), units_sold(n), revenue(n*p){ }
    Sales_data(std::istream &is) { read(is, *this); }
    
    std::string isbn() const { return bookNo; };
    Sales_data& combine(const Sales_data&);
    
    std::string bookNo;
    unsigned units_sold = 0;
    double revenue = 0.0;
};

// member functions.
Sales_data& Sales_data::combine(const Sales_data& rhs)
{
    units_sold += rhs.units_sold;
    revenue += rhs.revenue;
    return *this;
}

// nonmember functions
std::istream &read(std::istream &is, Sales_data &item)
{
    double price = 0;
    is >> item.bookNo >> item.units_sold >> price;
    item.revenue = price * item.units_sold;
    return is;
}
~~~

### 7.13

~~~C++
#include "ex7_12.h"
int main()
{
    Sales_data total(std::cin);
    if (!total.isbn().empty())
    {
        std::istream &is = std::cin;
        while (is) {
            Sales_data trans(is);
            if (!is) break;
            if (total.isbn() == trans.isbn())
                total.combine(trans);
            else {
                print(std::cout, total) << std::endl;
                total = trans;
            }
        }
        print(std::cout, total) << std::endl;
    }
    else
    {
        std::cerr << "No data?!" << std::endl;
        return -1;
    }
    return 0;
}
~~~

### 7.14

~~~C++
Sales_data() : bookNo(""), units_sold(0) , revenue(0){}
~~~

### 7.15

~~~C++
class Person{
    string name;
    string address;
public:
    Person() = default;
    Person(const string s1,const string s2) : name(s1), address(s2){}
    Person(istream& is){ read(is, *this); }
    auto getName(){return name;}
    auto getAddress(){return address;}
};
istream& read(istream& is, Person& a){
    is >> a.name >> a.address;
    return is;
}
ostream& print(ostream& os, Person& a){
    os << a.name << " " << a.address;
    return os;
}
~~~

### 7.16

没有限制 & 指定的访问级别将直到下一个访问控制符亦或结束 & 所有可以被访问的部分都应该在 `public` 说明符之后 & 所有不能被类外访问但可被类内访问的应在 `private` 之后

### 7.17

有，默认访问控制不同， `class` 是 `private` ， `struct` 是 `public`

### 7.18

encapsulation is the separation of implementation from interface. It hides the implementation details of a type. (In C++, encapsulation is enforced by putting the implementation in the private part of a class)

------

Important advantages:

- User code cannot inadvertently corrupt the state of an encapsulation object.
- The implementation of an encapsulated class can change over time without requiring changes in user-level code.

### 7.19

~~~C++
class Person{
    string name;
    string address;
public:
    Person() = default;
    Person(const string s1,const string s2) : name(s1), address(s2){}
    Person(istream& is){ read(is, *this); }
    auto getName(){return name;}
    auto getAddress(){return address;}
};
istream& read(istream& is, Person& a){
    is >> a.name >> a.address;
    return is;
}
ostream& print(ostream& os, Person& a){
    os << a.name << " " << a.address;
    return os;
}
// the interface should be defined as public, the data shouldn't expose to outside of the class.
~~~

### 7.20

`friend` is a mechanism by which a class grants access to its nonpublic members. They have the same rights as members.

**Pros**:

- the useful functions can refer to class members in the class scope without needing to explicitly prefix them with the class name.
- you can access all the nonpublic members conveniently.
- sometimes, more readable to the users of class.

**Cons**:

- lessens encapsulation and therefore maintainability.
- code verbosity, declarations inside the class, outside the class.

### 7.21

~~~C++
class Sales_data {
friend std::istream &read(std::istream &is, Sales_data &item);
friend std::ostream &print(std::ostream &os, const Sales_data &item);
friend Sales_data add(const Sales_data &lhs, const Sales_data &rhs);
    
public:
    Sales_data() = default;
    Sales_data(const std::string &s):bookNo(s) { }
    Sales_data(const std::string &s, unsigned n, double p):bookNo(s), units_sold(n), revenue(n*p){ }
    Sales_data(std::istream &is) { read(is, *this); }
    
    std::string isbn() const { return bookNo; };
    Sales_data& combine(const Sales_data&);
    
private:
    std::string bookNo;
    unsigned units_sold = 0;
    double revenue = 0.0;
};

// member functions.
Sales_data& Sales_data::combine(const Sales_data& rhs)
{
    units_sold += rhs.units_sold;
    revenue += rhs.revenue;
    return *this;
}

// nonmember functions
std::istream &read(std::istream &is, Sales_data &item)
{
    double price = 0;
    is >> item.bookNo >> item.units_sold >> price;
    item.revenue = price * item.units_sold;
    return is;
}

std::ostream &print(std::ostream &os, const Sales_data &item)
{
    os << item.isbn() << " " << item.units_sold << " " << item.revenue;
    return os;
}

Sales_data add(const Sales_data &lhs, const Sales_data &rhs)
{
    Sales_data sum = lhs;
    sum.combine(rhs);
    return sum;
}
~~~

### 7.22

~~~C++
class Person{
friend istream& read(istream& is, Person& a);
friend ostream& print(ostream& os, Person& a);
private:
    string name;
    string address;
        
public:
    Person() = default;
    Person(const string s1,const string s2) : name(s1), address(s2){}
    Person(istream& is){ read(is, *this); }
    auto getName(){return name;}
    auto getAddress(){return address;}
};
istream& read(istream& is, Person& a){
    is >> a.name >> a.address;
    return is;
}
ostream& print(ostream& os, Person& a){
    os << a.name << " " << a.address;
    return os;
}
~~~

### 7.23 & 7.24

~~~C++
class Screen
{
public:
    using pos = string::size_type;
    Screen() = defualt;
    Screen(pos ht, pos wd) : height(ht), width(wd), contents(ht * wd, ' ') {}
    Screen(pos ht, pos wd, char c) : height(ht), width(wd), contents(ht * wd, c) {}
    char get() { return contents[cur]; }
    char get(pos r, pos c) { return contents[r * width + c]; }

private:
    pos cur = 0;
    pos height = 0, width = 0;
    string contents;
};
~~~

### 7.25

The class below can rely on it. It goes in *Section 7.1.5*:

> the synthesized versions are unlikely to work correctly for classes that allocate resources that reside outside the class objects themselves.

> Moreover, the synthesized versions for copy, assignment, and destruction work correctly for classes that have **vector or string members**.

Hence the class below which used only built-in type and strings can rely on the default version of copy and assignment.

### 7.26

~~~C++
class Sales_data
{
    friend std::istream &read(std::istream &is, Sales_data &item);
    friend std::ostream &print(std::ostream &os, const Sales_data &item);
    friend Sales_data add(const Sales_data &lhs, const Sales_data &rhs);

public:
    Sales_data() = default;
    Sales_data(const std::string &s) : bookNo(s) {}
    Sales_data(const std::string &s, unsigned n, double p) : bookNo(s), units_sold(n), revenue(n * p) {}
    Sales_data(std::istream &is) { read(is, *this); }

    std::string isbn() const { return bookNo; };
    Sales_data &combine(const Sales_data &);

private:
    inline double avg_price() const;

private:
    std::string bookNo;
    unsigned units_sold = 0;
    double revenue = 0.0;
};

// member functions.
inline double avg_price() const
{
    return units_sold ? revenue / units_sold : 0;
}

Sales_data &Sales_data::combine(const Sales_data &rhs)
{
    units_sold += rhs.units_sold;
    revenue += rhs.revenue;
    return *this;
}

// nonmember functions
std::istream &read(std::istream &is, Sales_data &item)
{
    double price = 0;
    is >> item.bookNo >> item.units_sold >> price;
    item.revenue = price * item.units_sold;
    return is;
}

std::ostream &print(std::ostream &os, const Sales_data &item)
{
    os << item.isbn() << " " << item.units_sold << " " << item.revenue;
    return os;
}

Sales_data add(const Sales_data &lhs, const Sales_data &rhs)
{
    Sales_data sum = lhs;
    sum.combine(rhs);
    return sum;
}
~~~

### 7.27

~~~C++
class Screen
{
public:
    using pos = string::size_type;
    Screen() = defualt;
    Screen(pos ht, pos wd) : height(ht), width(wd), contents(ht * wd, ' ') {}
    Screen(pos ht, pos wd, char c) : height(ht), width(wd), contents(ht * wd, c) {}
    char get() { return contents[cur]; }
    char get(pos r, pos c) { return contents[r * width + c]; }
    Screen &move(pos l, pos r)
    {
        cur = l * width + r;
        return *this;
    }
    Screen &set(char c)
    {
        contents[cur] = c;
        return *this;
    }
    Screen &set(pos l, pos r, char c)
    {
        contents[l * width + r] = c;
        return *this;
    }
    Screen &display(ostream &os)
    {
        do_display(os);
        return *this;
    }
    Screen &display(ostream &os) const
    {
        do_display(os);
        return *this;
    }

private:
    void do_display const(ostream &os)
    {
        os << contents;
    }

private:
    pos cur = 0;
    pos height = 0, width = 0;
    string contents;
};
~~~

### 7.28

The second call to `display` couldn't print `#` among the output, cause the call to `set` would change the **temporary copy**, not myScreen.

### 7.29

Yes

### 7.30

**Pros**

- more explicit

- less scope for misreading

- can use the member function parameter which name is same as the member name.

    ```c++
      void setAddr(const std::string &addr) { this->addr = addr; }
    ```

**Cons**

- more to read

- sometimes redundant

    ```c++
      std::string getAddr() const { return this->addr; } // unnecessary
    ```

### 7.31

~~~C++
class Y;

class X {
    Y* y = nullptr;
};

class Y {
    X x;
};
~~~

### 7.32

~~~C++
class Screen;

class Window_mgr {
public:
    using ScreenIndex = std::vector<Screen>::size_type;
    inline void clear(ScreenIndex);
private:
    std::vector<Screen> screens;
};

class Screen {
    friend void Window_mgr::clear(ScreenIndex);
    
public:
    using pos = std::string::size_type;

    Screen() = default;
    Screen(pos ht, pos wd):height(ht), width(wd), contents(ht*wd, ' '){ }
    Screen(pos ht, pos wd, char c):height(ht), width(wd), contents(ht*wd, c){ }

    char get() const { return contents[cursor]; }
    char get(pos r, pos c) const { return contents[r*width+c]; }
    inline Screen& move(pos r, pos c);
    inline Screen& set(char c);
    inline Screen& set(pos r, pos c, char ch);

    const Screen& display(std::ostream &os) const { do_display(os); return *this; }
    Screen& display(std::ostream &os) { do_display(os); return *this; }

private:
    void do_display(std::ostream &os) const { os << contents; }

private:
    pos cursor = 0;
    pos height = 0, width = 0;
    std::string contents;
};

inline void Window_mgr::clear(ScreenIndex i)
{ 
    if (i >= screens.size()) return;    // judge for out_of_range.
    Screen &s = screens[i];
    s.contents = std::string(s.height * s.width, ' ');
}

inline Screen& Screen::move(pos r, pos c)
{
    cursor = r*width + c;
    return *this;
}

inline Screen& Screen::set(char c)
{
    contents[cursor] = c;
    return *this;
}

inline Screen& Screen::set(pos r, pos c, char ch)
{
    contents[r*width+c] = ch;
    return *this;
}
~~~

### 7.33

~~~C++
Screen::pos Screen::size() const
{
    return height * width;
}
~~~

### 7.34

~~~C++
D:\WorkSpace\C++\A.cpp:8:20: 错误：‘pos’未声明
     void dummy_fcn(pos height)
                    ^~~
~~~

### 7.35

~~~C++
typedef string Type;
Type initVal();
class Exercise
{
public:
    typedef double Type;
    Type setVal(Type);
    Type initVal();

private:
    int val;
};
Exercise::Type Exercise::initVal()
{
    return 0;
}
Exercise::Type Exercise::setVal(Type a)
{
    val += a + initVal();
    return val;
}
~~~

### 7.36

~~~C++
struct X{
    X(int i, int j): base(i), rem(i % j){}
    int rem, base;
}
~~~

### 7.37

~~~C++
Sales_data first_item(cin);   // use Sales_data(std::istream &is) ; its value are up to your input.

int main() {
  Sales_data next;  // use Sales_data(std::string s = ""); bookNo = "", cnt = 0, revenue = 0.0
  Sales_data last("9-999-99999-9"); // use Sales_data(std::string s = ""); bookNo = "9-999-99999-9", cnt = 0, revenue = 0.0
}
~~~

### 7.38

~~~C++
Sale_data(istream& is = std::cin){read(is,*this);}
~~~

### 7.39

illegal. cause the call of overloaded 'Sales_data()' is **ambiguous**.

### 7.40

~~~C++
class Book 
{
public:
    Book(unsigned isbn, std::string const& name, std::string const& author, std::string const& pubdate)
        :isbn_(isbn), name_(name), author_(author), pubdate_(pubdate)
    { }

    explicit Book(std::istream &in) 
    { 
        in >> isbn_ >> name_ >> author_ >> pubdate_;
    }

private:
    unsigned isbn_;
    std::string name_;
    std::string author_;
    std::string pubdate_;
};
~~~

### 7.41

~~~C++
// ex7_41.h
#ifndef CP5_ex7_41_h
#define CP5_ex7_41_h

#include <string>
#include <iostream>

class Sales_data {
    friend std::istream &read(std::istream &is, Sales_data &item);
    friend std::ostream &print(std::ostream &os, const Sales_data &item);
    friend Sales_data add(const Sales_data &lhs, const Sales_data &rhs);

public:
    Sales_data(const std::string &s, unsigned n, double p):bookNo(s), units_sold(n), revenue(n*p)
    { std::cout << "Sales_data(const std::string&, unsigned, double)" << std::endl; }
    
    Sales_data() : Sales_data("", 0, 0.0f)
    { std::cout << "Sales_data()" << std::endl; }
    
    Sales_data(const std::string &s) : Sales_data(s, 0, 0.0f)
    { std::cout << "Sales_data(const std::string&)" << std::endl; }
    
    Sales_data(std::istream &is);

    std::string isbn() const { return bookNo; }
    Sales_data& combine(const Sales_data&);
    
private:
    inline double avg_price() const;        

private:
    std::string bookNo;
    unsigned units_sold = 0;
    double revenue = 0.0;
};

inline
double Sales_data::avg_price() const
{
    return units_sold ? revenue/units_sold : 0;
}

// declarations for nonmember parts of the Sales_data interface.
std::istream &read(std::istream &is, Sales_data &item);
std::ostream &print(std::ostream &os, const Sales_data &item);
Sales_data add(const Sales_data &lhs, const Sales_data &rhs);

#endif

// ex7_41.cpp
#include "ex7_41.h"

// constructor
Sales_data::Sales_data(std::istream &is) : Sales_data()
{
    std::cout << "Sales_data(istream &is)" << std::endl;
    read(is, *this);
}

// member functions.
Sales_data& Sales_data::combine(const Sales_data& rhs)
{
    units_sold += rhs.units_sold;
    revenue += rhs.revenue;
    return *this;
}

// friend functions
std::istream &read(std::istream &is, Sales_data &item)
{
    double price = 0;
    is >> item.bookNo >> item.units_sold >> price;
    item.revenue = price * item.units_sold;
    return is;
}

std::ostream &print(std::ostream &os, const Sales_data &item)
{
    os << item.isbn() << " " << item.units_sold << " " << item.revenue;
    return os;
}

Sales_data add(const Sales_data &lhs, const Sales_data &rhs)
{
    Sales_data sum = lhs;
    sum.combine(rhs);
    return sum;
}
~~~

### 7.42

~~~C++
class Book 
{
public:
    Book(unsigned isbn, std::string const& name, std::string const& author, std::string const& pubdate)
        :isbn_(isbn), name_(name), author_(author), pubdate_(pubdate)
    { }

    explicit Book(std::istream &in) 
    { 
        in >> isbn_ >> name_ >> author_ >> pubdate_;
    }

private:
    unsigned isbn_;
    std::string name_;
    std::string author_;
    std::string pubdate_;
};
~~~

### 7.43

~~~C++
class NoDefault {
public:
    NoDefault(int i) { }
};

class C {
public:
    C() : def(0) { } // define the constructor of C.
private:
    NoDefault def;
};

int main()
{
    C c;   
    std::vector<C> vec(10); 
    return 0;
}
~~~

### 7.44

~~~C++
vector<NoDefault> vec(10);
// illegal, cause there are ten elements, each would be default initialized. But no default initializer for the temporary object.
~~~

### 7.45

No problem. cause `C` have the default constructor.

### 7.46

- a) A class must provide at least one constructor. (**untrue**, "The compiler-generated constructor is known as the synthesized default constructor.")
- b) A default constructor is a constructor with an empty parameter list. (**untrue**, A default constructor is a constructor that is used if no initializer is supplied.What's more, A constructor that supplies default arguments for all its parameters also defines the default constructor)
- c) If there are no meaningful default values for a class, the class should not provide a default constructor. (**untrue**, the class should provide.)
- d) If a class does not define a default constructor, the compiler generates one that initializes each data member to the default value of its associated type. (**untrue**, only if our class does not explicitly define **any constructors**, the compiler will implicitly define the default constructor for us.)

### 7.47

Whether the conversion of a `string` to `Sales_data` is desired **depends on how we think our users will use the conversion**. In this case, it might be okay. The `string` in null_book probably represents a nonexistent ISBN.

Benefits:

- prevent the use of a constructor in a context that requires an implicit conversion
- we can define a constructor which is used only with the direct form of initialization

Drawbacks:

- meaningful only on constructors that can be called with a single argument

### 7.48

Both are nothing happened.

### 7.49

~~~C++
(a) Sales_data &combine(Sales_data); // ok
(b) Sales_data &combine(Sales_data&); // [Error] no matching function for call to 'Sales_data::combine(std::string&)' (`std::string&` can not convert to `Sales_data` type.)  
(c) Sales_data &combine(const Sales_data&) const; // The trailing const mark can't be put here, as it forbids any mutation on data members. This conflicts with combine's semantics.
/*
Some detailed explanation about problem (b) :It's wrong. Because combine’s parameter is a non-const reference , we can't pass a temporary to that parameter. If combine’s parameter is a reference to const , we can pass a temporary to that parameter. Like this :Sales_data &combine(const Sales_data&); Here we call the Sales_data combine member function with a string argument. This call is perfectly legal; the compiler automatically creates a Sales_data object from the given string. That newly generated (temporary) Sales_data is passed to combine.
*/
~~~

### 7.50

~~~C++
struct Person {
    friend std::istream &read(std::istream &is, Person &person);
    friend std::ostream &print(std::ostream &os, const Person &person);

public:
    Person() = default;
    Person(const std::string sname, const std::string saddr):name(sname), address(saddr){ }
    explicit Person(std::istream &is){ read(is, *this); }

    std::string getName() const { return name; }
    std::string getAddress() const { return address; }
private:
    std::string name;
    std::string address;
};

std::istream &read(std::istream &is, Person &person)
{
    is >> person.name >> person.address;
    return is;
}

std::ostream &print(std::ostream &os, const Person &person)
{
    os << person.name << " " << person.address;
    return os;
}
~~~

### 7.51

Such as a function like that:

```c++
int getSize(const std::vector<int>&);
```

if vector has not defined its single-argument constructor as explicit. we can use the function like:

```c++
getSize(34);
```

What is this mean? It's very confused.

But the `std::string` is different. In ordinary, we use `std::string` to replace `const char *`(the C language). so when we call a function like that:

```c++
void setYourName(std::string); // declaration.
setYourName("pezy"); // just fine.
```

it is very natural.

### 7.52

~~~C++
struct Sales_data {
    std::string bookNo;
    unsigned units_sold;
    double revenue;
};
~~~

### 7.53

~~~C++
class Debug {
public:
    constexpr Debug(bool b = true) : rt(b), io(b), other(b) { }
    constexpr Debug(bool r, bool i, bool o) : rt(r), io(i), other(o) { }
    constexpr bool any() { return rt || io || other; }
    
    void set_rt(bool b) { rt = b; }
    void set_io(bool b) { io = b; }
    void set_other(bool b) { other = b; }
    
private:
    bool rt;        // runtime error
    bool io;        // I/O error
    bool other;     // the others
};
~~~

### 7.54

In C++11, constexpr member functions are implicitly const, so the "set_xx" functions, which will modify data members, cannot be declared as constexpr. 

In C++14, this property no longer holds, so constexpr is suitable.

### 7.55

~~~C++
// no.
// std::string is not a literal type, and it can be verified by following codes:

#include <string>
#include <iostream>
#include <type_traits>

struct Data {
    int ival;
    std::string s;
};

int main()
{
    std::cout << std::boolalpha;
    std::cout << std::is_literal_type<Data>::value << std::endl;
    // output: false
}
~~~

### 7.56

> What is a static class member?

A class member that is **associated with the class**, rather than with individual objects of the class type.

> What are the advantages of static members?

each object can no need to store a common data. And if the data is changed, each object can use the new value.

> How do they differ from ordinary members?

- a static data member can have **incomplete type**.
- we can use a static member **as a default argument**.

### 7.57

~~~C++
class Account {
public:
    void calculate() { amount += amount * interestRate; }
    static double rate() { return interestRate; }
    static void rate(double newRate) { interestRate = newRate; }
    
private:
    std::string owner;
    double amount;
    static double interestRate;
    static constexpr double todayRate = 42.42;
    static double initRate() { return todayRate; }
};

double Account::interestRate = initRate();
~~~

### 7.58

~~~C++
// example.h
class Example{
public:
    static double rate = 6.5;
    static const int vecSize = 20;
    static vector<double> vec(vecSize);
};

// example.c
#include "example.h"
double Example::rate;
vector<double> Example::vec;

/*
D:\WorkSpace\C++\A.cpp:7:19: 错误：‘constexpr’ needed for in-class initialization of static data member ‘double Example::rate’ of non-integral type [-fpermissive]
     static double rate = 6.5;
                   ^~~
D:\WorkSpace\C++\A.cpp:9:31: 错误：‘vecSize’不是一个类型
     static vector<double> vec(vecSize);
                               ^~~
D:\WorkSpace\C++\A.cpp:13:25: 错误：‘std::vector<double> Example::vec’ is not a static data member of ‘class Example’
 vector<double> Example::vec;
                         ^~~
*/

// example.h
class Example {
public:
    static constexpr double rate = 6.5;
    static const int vecSize = 20;
    static vector<double> vec;
};

// example.C
#include "example.h"
constexpr double Example::rate;
vector<double> Example::vec(Example::vecSize);
~~~

## 第八章

### 8.1

~~~C++
istream& fun(istream& is){
    string buf;
    while(is >> buf)
        cout << buf << endl;
    is.clear();
}
~~~

### 8.2

~~~C++
istream& fun(istream& is){
    string buf;
    while(is >> buf)
        cout << buf << endl;
    is.clear();
}
int main(){
    istream& is = fun(cin);
    cout << is.rdstate() << endl;
    return 0;
}
~~~

### 8.3

putting `cin` in an error state cause to terminate. such as `eofbit`, `failbit` and `badbit`.

### 8.4

~~~C++
vector<string> vec;
void fun(string fileName){
    ifstream f1(fileName);
    if(f1){
        string a;
        while(getline(f1, a)){
            vec.push_back(a);
        }
    }else 
        cerr << "can not open the file : " << fileName << endl; 
}
~~~

### 8.5

~~~C++
vector<string> vec;
void fun(string fileName){
    ifstream f1(fileName);
    if(f1){
        string a;
        while(f1 >> a){
            vec.push_back(a);
        }
    }else 
        cerr << "can not open the file : " << fileName << endl; 
}
~~~

### 8.6

~~~C++
#include "../ch07/ex7_26.h"
using std::ifstream; using std::cout; using std::endl; using std::cerr;
int main(int argc, char **argv)
{
    ifstream input(argv[1]);
    Sales_data total;
    if (read(input, total))
    {
        Sales_data trans;
        while (read(input, trans))
        {
            if (total.isbn() == trans.isbn())
                total.combine(trans);
            else
            {
                print(cout, total) << endl;
                total = trans;
            }
        }
        print(cout, total) << endl;
    }
    else
        cerr << "No data?!" << endl;
    return 0;
}
~~~

### 8.7

~~~C++
#include "../ch07/ex7_26.h"
using std::ifstream; using std::ofstream; using std::endl; using std::cerr;
int main(int argc, char **argv)
{
    ifstream input(argv[1]);
    ofstream output(argv[2]);
    Sales_data total;
    if (read(input, total))
    {
        Sales_data trans;
        while (read(input, trans))
        {
            if (total.isbn() == trans.isbn())
                total.combine(trans);
            else
            {
                print(output, total) << endl;
                total = trans;
            }
        }
        print(output, total) << endl;
    }
    else
        cerr << "No data?!" << endl;   
    return 0;
}
~~~

### 8.8

~~~C++
ofstream output(argv[2], ofstream::app);
~~~

### 8.9

~~~C++
istream& fun(istream& is){
    string buf;
    while(is >> buf)
        cout << buf << endl;
    is.clear();
}
int main(){
    istringstream iss("ATest");
    fun(iss);
    return 0;
}
~~~

### 8.10

~~~C++
string fname,line;
vector<string> vec;
ifstream ifs(fname);
if(!ifs){
    cerr << "No data" << endl;
    exit(0);
}
while(getline(ifs,line))
    vec.push_back(line);
for(auto &s : vec){
    istringstream iss(s);
    string s;
    while(iss >> s)
        cout << s << endl;
}
~~~

### 8.11

~~~C++
#include <bits/stdc++.h>
using namespace std;

struct PersonInfo
{
    string name;
    vector<string> phones;
};

int main()
{
    string line, word;
    vector<PersonInfo> people;
    istringstream record;
    while (getline(cin, line))
    {
        PersonInfo info;
        record.clear();
        record.str(line);
        record >> info.name;
        while (record >> word)
            info.phones.push_back(word);
        people.push_back(info);
    }

    for (auto &p : people)
    {
        std::cout << p.name << " ";
        for (auto &s : p.phones)
            std::cout << s << " ";
        std::cout << std::endl;
    }

    return 0;
}
~~~

### 8.12

Cause we need a aggregate class here. so it should have no in-class initializers.

### 8.13

~~~C++
#include <bits/stdc++.h>
using namespace std;

struct PersonInfo {
    string name;
    vector<string> phones;
};

bool valid(const string& str)
{
    return isdigit(str[0]);
}

string format(const string& str)
{
    return str.substr(0,3) + "-" + str.substr(3,3) + "-" + str.substr(6);
}

int main()
{
    ifstream ifs("../data/phonenumbers.txt");
    if (!ifs)
    {
        cerr << "no phone numbers?" << endl;
        return -1;
    }

    string line, word;
    vector<PersonInfo> people;
    istringstream record;
    while (getline(ifs, line))
    {
        PersonInfo info;
        record.clear();
        record.str(line);
        record >> info.name;
        while (record >> word)
            info.phones.push_back(word);
        people.push_back(info);
    }

    for (const auto &entry : people)
    {
        ostringstream formatted, badNums;
        for (const auto &nums : entry.phones)
            if (!valid(nums)) badNums << " " << nums;
            else formatted << " " << format(nums);
        if (badNums.str().empty())
            cout << entry.name << " " << formatted.str() << endl;
        else
            cerr << "input error: " << entry.name
                 << " invalid number(s) " << badNums.str() << endl;
    }

    return 0;
}
~~~

### 8.14

- cause they are all class type, not the built-in type. so **reference** more effective.
- output shouldn't change their values. so we added the `const`.

## 第九章

### 9.1

list & deque & vector

### 9.2

~~~C++
list<deque<int>> Alist;
~~~

### 9.3

two iterators, `begin` and `end`:

- they refer to elements of the same container.
- It is possible to reach `end` by repeatedly incrementing `begin`.

### 9.4

~~~C++
bool fun(vector<int>::iterator begin, vector<int>::iterator end, int val){
    for(; begin!=end; begin++)
        if(*begin == val)
            return true;
    return false;
}
~~~

### 9.5

~~~C++
vector<int>::iterator fun(vector<int>::iterator begin, vector<int>::iterator end, int val){
    for(; begin!=end; begin++)
        if(*begin == val)
            return begin;
    return end;
}
~~~

### 9.6

~~~C++
list<int> lst1;
list<int>::iterator iter1 = lst1.begin(), iter2 = lst1.end();
while(iter1 != iter2);
//operator < is not implemented in std::list, because std::list is essetially a doubly linked list. Addresses of nodes of linked list are not necessarily continuous.
~~~

### 9.7

~~~C++
vector<int>::size_type;
~~~

### 9.8

~~~C++
list<string>::const_iterator cit;
list<string>::iterator it;
~~~

### 9.9

`cbegin` is a const member that returns the container’s **const_iterator** type.

`begin` is nonconst and returns the container’s **iterator** type.

### 9.10

~~~C++
vector<int> v1;
const vector<int> v2;
auto it1 = v1.begin();// vector<int>::iterator
auto it2 = v2.begin(), it3 = v1.cbegin(), it4 = v2.cbegin();// vector<int>::const_iterator
~~~

### 9.11

~~~C++
vector<int> vec;    // vec is empty
vector<int> vec(10);    // 0
vector<int> vec(10, 1);  // 1
vector<int> vec{1, 2, 3, 4, 5}; // 1, 2, 3, 4, 5
vector<int> vec(other_vec); // same as other_vec
vector<int> vec(other_vec.begin(), other_vec.end()); // same as other_vec.begin to %.end
~~~

### 9.12

The constructor that takes another container as an argument (excepting array) assumes the container type and element type of both containers are identical. It will also copy all the elements of the received container into the new one:

```c++
list<int> numbers = { 1, 2, 3, 4, 5 };
list<int> numbers2(numbers);        // ok, numbers2 has the same elements as numbers
vector<int> numbers3(numbers);      // error: no matching function for call...
list<double> numbers4(numbers);     // error: no matching function for call...
```

The constructor that takes two iterators as arguments does not require the container types to be identical. Moreover, the element types in the new and original containers can differ as long as it is possible to convert the elements we’re copying to the element type of the container we are initializing. It will also copy only the object delimited by the received iterators.

```c++
list<int> numbers = { 1, 2, 3, 4, 5 };
list<int> numbers2(numbers.begin(), numbers.end);        // ok, numbers2 has the same elements as numbers
vector<int> numbers3(numbers.begin(), --numbers.end());  // ok, numbers3 is { 1, 2, 3, 4 }
list<double> numbers4(++numbers.beg(), --numbers.end());        // ok, numbers4 is { 2, 3, 4 }
forward_list<float> numbers5(numbers.begin(), numbers.end());   // ok, number5 is { 1, 2, 3, 4, 5 }
```

### 9.13

~~~C++
#include<bits/stdc++.h>
using namespace std;
int main(){
    list<int> a(10, 1);
    vector<double> a1(a.begin(), a.end());
    
    vector<int> b(10, 2);
    vector<double> b1(b.begin(), b.end());
    return 0;
}
~~~

### 9.14

~~~C++
#include <bits/stdc++.h>
using namespace std;
typedef long long ll;
const int N = 2e6 + 5;
ll num[N];
int main()
{
    list<char *> a{"Mooophy", "pezy", "Queeuqueg"};
    vector<string> b;
    b.assign(a.cbegin(), a.cend());
    for (auto &it : b)
        cout << it << endl;
    return 0;
}
~~~

### 9.15

~~~C++
vector<int> a;
vector<int> b;
if(a == b)
    puts("Yes");
else 
    puts("No");
~~~

### 9.16

~~~C++
list<int>      li{ 1, 2, 3, 4, 5 };
vector<int>    vec{ 1, 2, 3, 4, 5 };
cout << (vector<int>(li.begin(), li.end()) == vec ? "true" : "false") << endl;
~~~

### 9.17

必须有相同的容器和相同的类型，所持有的类型必须支持关系操作。

### 9.18

~~~C++
string s;
deque<string> de;
while(cin >> s)
    de.push_back(s);
for(auto it = de.cbegin(); it != de.cend(); it++)
    cout << *it << endl;
~~~

### 9.19

~~~c++
string s;
list<string> li;
while(cin >> s)
    li.push_back(s);
for(auto it = li.cbegin(); it != li.cend(); it++)
    cout << *it << endl;
~~~

### 9.20

~~~C++
list<int> li{ 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
deque<int> odd, even;
for(auto i : li)
    (i & 0x1 ? odd : even).push_back(i);
~~~

### 9.21

第一个 `insert` 调用接受刚读取的字符串，并将其放在 `iter` 所表示的元素的前面，`insert` 返回的值是指向这个新元素的迭代器。将该迭代器赋值给 `iter`，然后重复 `while` ，读取另一个单词。

只要有单词要插入，每次遍历 `while` 都会在 `iter` 前面插入一个新元素，并将新插入元素的位置重新赋值给 `iter` 即可。

### 9.22

~~~C++
vector<int>::iterator iter = iv.begin(), mid = iv.begin + iv.size()/2;
while(iter != mid)// 死循环
    if(*iter == some_val)
        mid = iv.insert(iter, 2 * some_val);// 插入操作后，mid迭代器失效

// Fixed
void double_and_insert(std::vector<int>& v, int some_val)
{
    auto mid = [&]{ return v.begin() + v.size() / 2; };
    for (auto curr = v.begin(); curr != mid(); ++curr)
        if (*curr == some_val)
            ++(curr = v.insert(curr, 2 * some_val));
}
int main()
{
    std::vector<int> v{ 1, 9, 1, 9, 9, 9, 1, 1 };
    double_and_insert(v, 1);

    for (auto i : v) 
        std::cout << i << std::endl;
}
~~~

### 9.23

同一个元素

### 9.24

~~~C++
vector<int> a;
a.at(0), a[0], a.front(), a.end();
// terminating with uncaught exception of type std::out_of_range
// Segmentation fault: 11
// Segmentation fault: 11
// Segmentation fault: 11
~~~

### 9.25

不会发生什么事情 & 从 `elem1` 删到最后 & 同首

### 9.26

~~~C++
int ia[] = { 0, 1, 1, 2, 3, 5, 8, 13, 21, 55, 89 };
vector<int> a(ia, end(ia));
list<int> b(a.begin(), a.end());
auto it = b.begin();
while(it != b.end())
    if(*it & 0x1)
        it = b.erase(it);
    else
        it++;
auto i = a.begin();
while(i != a.end())
    if(!(*it & 0x1))
        i = a.erase(it);
    else
        i++;
~~~

### 9.27

~~~C++
auto remove_odds(forward_list<int>& flist)
{
    auto is_odd = [] (int i) { return i & 0x1; };
    flist.remove_if(is_odd);
}

int main()
{
    forward_list<int> data { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
    remove_odds(data);
    for (auto i : data) 
        cout << i << " ";
    return 0;
}
~~~

### 9.28

~~~C++
auto fun(forward_list<string> &lst, string &a, string &b){
    auto prev = lst.before_begin();
    for (auto curr = lst.begin(); curr != lst.end(); prev = curr++)
    {
        if (*curr == to_find)
        {
            lst.insert_after(curr, to_add);
            return;
        }
    }
    lst.insert_after(prev, to_add);
}
~~~

### 9.29

~~~C++
vec.resize(100);    // 在25个元素后增加75个0
vec.resize(10);     // 只保留前10个元素
~~~

### 9.30

有默认的初始化或者相应的构造函数

### 9.31

~~~C++
// list
auto remove_evens_and_double_odds(list<int>& data)
{
    for(auto cur = data.begin(); cur != data.end();)
        if (*cur & 0x1)
            cur = data.insert(cur, *cur), advance(cur, 2);
        else
            cur = data.erase(cur);
}

int main()
{
    list<int> data { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
    remove_evens_and_double_odds(data);
    for (auto i : data) cout << i << " ";

    return 0;
}

// forward_list
auto remove_evens_and_double_odds(forward_list<int>& data)
{
    for(auto cur = data.begin(), prv = data.before_begin(); cur != data.end();)
        if (*cur & 0x1)
            cur = data.insert_after(prv, *cur),
            advance(cur, 2),
            advance(prv, 2);
        else
            cur = data.erase_after(prv);
}

int main()
{
    forward_list<int> data { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
    remove_evens_and_double_odds(data);
    for (auto i : data)
        cout << i << " ";

    return 0;
}
~~~

### 9.32

the statement is illegal, because as said in Standard [5.2.2] : "The order of evaluation of arguments is unspecified." As a result, after entering function insert, iter could be its original value or original value + 1 or even anything else, depending on how compiler implemented. 

### 9.33

~~~C++
vector<int> v{ 1, 2, 3, 4, 5, 6, 7, 8, 9 };
auto begin = v.begin();
while (begin != v.end()) 
{
    ++begin;
    /*begin = */v.insert(begin, 42);
    ++begin;
}
for (auto i : v)
    cout << i << " ";
~~~

### 9.34

~~~C++
iter = vi.begin();
while(iter != vi.end())
    if(*iter % 2)
        iter = vi.insert(iter, *iter);
    ++iter;

//FIXED
vector<int> data { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
for(auto cur = data.begin(); cur != data.end(); ++cur)
    if(*cur & 0x1)
        cur = data.insert(cur, *cur), ++cur;

for (auto i : data)
    cout << i << " ";
~~~

### 9.35

`size` 是目前保存的元素数量

`capacity` 是在必须重新申请内存之前能存储的最大元素数量

### 9.36

not

### 9.37

`list` 不连续存储数据

`array` 是固定的大小

### 9.38

~~~C++
vector<string> v;
for (string buffer; cin >> buffer; v.push_back(buffer))
    cout << v.capacity() << endl;
~~~

### 9.39

~~~C++
vector<string> svec;
svec.reserve(1024);
string word;
while(cin >> word)
    svec.push_back(word);
svec.resize(svec.size() + svec.size()/2);
/*
The while loop will read words from cin and store them in out vector. Even if we initially reserved 1024 elements, if there are more words read from cin, our vector's capacity will be automatically increased (most implementations will double the previous capacity) to accommodate them.

And now comes the catch. resize() is different from reserve(). In this case resize() will add another svec.size()/2 value initialized elements to svec. If this exceeds svec.capacity() it will also automatically increase it to accommodate the new elements.
*/
~~~

### 9.40

| read | size |      capacity       |
| :--: | :--: | :-----------------: |
| 256  | 384  |        1024         |
| 512  | 768  |        1024         |
| 1000 | 1500 | 2000(clang is 2048) |
| 1048 | 1572 |        2048         |

### 9.41

~~~C++
vector<char> v{ 'h', 'e', 'l', 'l', 'o' };
string str(v.cbegin(), v.cend());
cout << str << endl;
~~~

### 9.42

`str.reserve(120)`

### 9.43

~~~C++
void replace_with(string &s, string const& oldVal, string const& newVal)
{
    for (auto cur = s.begin(); cur <= s.end() - oldVal.size(); )
        if (oldVal == string{ cur, cur + oldVal.size() })
            cur = s.erase(cur, cur + oldVal.size()),
            cur = s.insert(cur, newVal.begin(), newVal.end()),
            cur += newVal.size();
        else  
            ++cur;
}
int main()
{
    string s{ "To drive straight thru is a foolish, tho courageous act." };
    replace_with(s, "tho", "though");
    replace_with(s, "thru", "through");
    cout << s << endl;
    return 0;
}
~~~

### 9.44

~~~C++
void replace_with(string &s, string const& oldVal, string const& newVal)
{
    for (size_t pos = 0; pos <= s.size() - oldVal.size();)
        if (s[pos] == oldVal[0] && s.substr(pos, oldVal.size()) == oldVal)
            s.replace(pos, oldVal.size(), newVal),
            pos += newVal.size();
        else
            ++pos;
}
int main()
{
    string s{ "To drive straight thru is a foolish, tho courageous act." };
    replace_with(s, "tho", "though");
    replace_with(s, "thru", "through");
    cout << s << endl;
    return 0;
}
~~~

### 9.45

~~~C++
string fun(string s, string const& a, string const& b){
    s.insert(s.begin, a.begin(), a.end());
    return s.append(b);
}
~~~

### 9.46

~~~C++
string fun(string s, string const& pre, string const& su)
{
    s.insert(0, pre);
    s.insert(s.size(), su);
    return s;
}
~~~

### 9.47

~~~C++
// find_first_of
string numbers{ "123456789" };
string alphabet{ "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ" };
string str{ "ab2c3d7R4E6" };

cout << "numeric characters: ";
for (int pos = 0; (pos = str.find_first_of(numbers, pos)) != string::npos; ++pos)
    cout << str[pos] << " ";
cout << "\nalphabetic characters: ";
for (int pos = 0; (pos = str.find_first_of(alphabet, pos)) != string::npos; ++pos)
    cout << str[pos] << " ";
cout << endl;

// find_first_not_of
string numbers{ "0123456789" };
string alphabet{ "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ" };
string str{ "ab2c3d7R4E6" };

cout << "numeric characters: ";
for (int pos = 0; (pos = str.find_first_not_of(alphabet, pos)) != string::npos; ++pos)
    cout << str[pos] << " ";
cout << "\nalphabetic characters: ";
for (int pos = 0; (pos = str.find_first_not_of(numbers, pos)) != string::npos; ++pos)
    cout << str[pos] << " ";
cout << endl;
~~~

### 9.48

`string::npos`

### 9.49

~~~C++
ifstream ifs("../data/letter.txt");
if (!ifs) return -1;

string longest;
auto update_with = [&longest](string const& curr)
{
    if (string::npos == curr.find_first_not_of("aceimnorsuvwxz"))
        longest = longest.size() < curr.size() ? curr : longest;
};
for (string curr; ifs >> curr; update_with(curr));
cout << longest << endl;
~~~

### 9.50

~~~C++
auto sum_for_int(vector<string> const& v)
{
    int sum = 0;
    for (auto const& s : v)
        sum += stoi(s);
    return sum;
}

auto sum_for_float(vector<string> const& v)
{
    float sum = 0.0;
    for (auto const& s : v)
        sum += stof(s);
    return sum;
}

int main()
{
    vector<string> v = { "1", "2", "3", "4.5" };
    cout << sum_for_int(v) << endl;
    cout << sum_for_float(v) << endl;

    return 0;
}
~~~

### 9.51

~~~C++
using namespace std;
class My_date{
private:
    unsigned year, month, day;
public:
    My_date(const string &s){

        unsigned tag;
        unsigned format;
        format = tag = 0;

        // 1/1/1900
        if(s.find_first_of("/")!= string :: npos)
        {
            format = 0x01;
        }

        // January 1, 1900 or Jan 1, 1900
        if((s.find_first_of(',') >= 4) && s.find_first_of(',')!= string :: npos){
            format = 0x10;
        }
        else{ // Jan 1 1900
            if(s.find_first_of(' ') >= 3
                && s.find_first_of(' ')!= string :: npos){
                format = 0x10;
                tag = 1;
            }
        }

        switch(format){

        case 0x01:
            day = stoi(s.substr(0, s.find_first_of("/")));
            month = stoi(s.substr(s.find_first_of("/") + 1, s.find_last_of("/")- s.find_first_of("/")));
            year = stoi(s.substr(s.find_last_of("/") + 1, 4));

        break;

        case 0x10:
            if( s.find("Jan") < s.size() )  month = 1;
            if( s.find("Feb") < s.size() )  month = 2;
            if( s.find("Mar") < s.size() )  month = 3;
            if( s.find("Apr") < s.size() )  month = 4;
            if( s.find("May") < s.size() )  month = 5;
            if( s.find("Jun") < s.size() )  month = 6;
            if( s.find("Jul") < s.size() )  month = 7;
            if( s.find("Aug") < s.size() )  month = 8;
            if( s.find("Sep") < s.size() )  month = 9;
            if( s.find("Oct") < s.size() )  month =10;
            if( s.find("Nov") < s.size() )  month =11;
            if( s.find("Dec") < s.size() )  month =12;

            char chr = ',';
            if(tag == 1){
                chr = ' ';
            }
            day = stoi(s.substr(s.find_first_of("123456789"), s.find_first_of(chr) - s.find_first_of("123456789")));

            year = stoi(s.substr(s.find_last_of(' ') + 1, 4));
            break;
        }
    }

    void print(){
        cout << "day:" << day << " " << "month: " << month << " " << "year: " << year;
    }
};
int main()
{
    My_date d("Jan 1 1900");
    d.print();
    return 0;
}
~~~

### 9.52

~~~C++
int main()
{
    string expression{ "This is (pezy)." };
    bool bSeen = false;
    stack<char> stk;
    for (const auto &s : expression)
    {
        if (s == '(') { bSeen = true; continue; }
        else if (s == ')') bSeen = false;
        
        if (bSeen) stk.push(s);
    }
    
    string repstr;
    while (!stk.empty())
    {
        repstr += stk.top();
        stk.pop();
    }
    
    expression.replace(expression.find("(")+1, repstr.size(), repstr);
    
    cout << expression << endl;
    
    return 0;
}
~~~

## 第十章

### 10.1 & 10.2

~~~C++
// 10.1
vector<int> vec{ 1, 2, 3, 4, 5, 6, 6, 6, 2 };
cout << count(vec.begin(), vec.end(), 6);

// 10.2
list<string> v = { "aa", "aaa", "aa", "cc" };
cout << count(v.begin(), v.end(), "aa");
~~~

### 10.3 &10.4

~~~C++
// 10.3
vector<int> vec{ 1, 2, 3, 4, 5, 6, 6, 6, 2 };
int sum = accumulate(vec.cbegin(), vec.end(), 0);

// 10.4
vector<double> vd = { 1.1, 0.5, 3.3 };
cout<< accumulate(vd.cbegin(), vd.cend(), 0)<<endl;

// The ouput is 4 rather than 4.9 as expected.
// The reason is std::accumulate is a template function. 
// The third parameter is _Tp __init
// When "0" , an integer, had been specified here, the compiler deduced _Tp as
// interger.As a result , when the following statments were being excuted :
// for (; __first != __last; ++__first)
// __init = __init + *__first;
// return __init;
// all calculation would be converted to integer.
~~~

### 10.5

For such case, std::equal is going to compare the address value rather than the string value. So the result is not the same as std::string. Try to avoid coding this way. Check [#227](https://github.com/Mooophy/Cpp-Primer/issues/227) for more detail.

### 10.6

~~~C++
vector<int> vec{ 1, 2, 3, 4, 5, 6, 6, 6, 2 };
fill_n(vec.begin(), vec.end(), 0);
~~~

### 10.7

~~~C++
// a
vector<int> vec; list<int> lst; int i;
while(cin >> i)
    lst.push_back(i);
//copy(lst.cbegin(), lst.cend(), vec.begin());
copy(lst.cbegin(), lst.cend(), back_inserter(vec));

// b
vector<int> vec;
vec.reserve(10);
fill_n(vec.begin(), 10, 0);
~~~

### 10.8

Inserters like `back_inserter` is part of `<iterator>` rather than `<algorithm>`.

### 10.9

~~~C++
template<typename Sequence>
auto println(Sequence const& seq) -> std::ostream&
{
    for (auto const& elem : seq) 
        std::cout << elem << " ";
    return std::cout << std::endl;
}
void elimDups(vector<int> &a)
{
    sort(a.begin(), a.end());
    println(vs);
    auto end = unique(a.begin(), a.end());
    println(vs);
    a.erase(end, a.end());
    println(vs);
}
~~~

### 10.10

将算法与容器分离开

### 10.11

~~~C++
template<typename Sequence>
inline ostream& println(Sequence const& seq)
{
    for(auto const& elem : seq) cout << elem << " ";
    cout << endl;
    return cout;
}
inline bool is_shorter(string const& lhs, string const& rhs)
{
    return  lhs.size() < rhs.size();
}
void elimdups(vector<string> &vs)
{
    sort(vs.begin(), vs.end());
    auto new_end = unique(vs.begin(), vs.end());
    vs.erase(new_end, vs.end());
}
int main()
{
    vector<string> v{ "1234", "1234", "1234", "Hi", "alan", "wang" };
    elimdups(v);
    stable_sort(v.begin(), v.end(), is_shorter);
    println(v);
    return 0;
}
~~~

### 10.12

~~~C++
#include "../ch07/ex7_26.h"     // Sales_data class.
inline bool compareIsbn(const Sales_data &sd1, const Sales_data &sd2)
{
    return sd1.isbn().size() < sd2.isbn().size();
}
int main()
{
    Sales_data d1("aa"), d2("aaaa"), d3("aaa"), d4("z"), d5("aaaaz");
    vector<Sales_data> v{ d1, d2, d3, d4, d5 };
    sort(v.begin(), v.end(), compareIsbn);
    for(const auto &element : v)
        cout << element.isbn() << " ";
    cout << endl;
    return 0;
}
~~~

### 10.13

~~~C++
bool predicate(const string &s) 
{ 
    return s.size() >= 5;
}
int main()
{
    auto v = vector<string>{ "a", "as", "aasss", "aaaaassaa", "aaaaaabba", "aaa" };
    auto pivot = partition(v.begin(), v.end(), predicate);
    for (auto it = v.cbegin(); it != pivot; ++it)
        cout << *it << " ";
    cout << endl;
    return 0;
}
~~~

### 10.14

~~~C++
auto add = [](int a, int b){return a + b;}
~~~

### 10.15

~~~c++
int a = 1;
auto add = [a](int b){return a + b;}
~~~

### 10.16

~~~C++
void biggies(vector<string> &s, vector<string>::size_type sz){
    sort(s.begin(), s.end(),[](const string &s1, const string &s2){
        return s1 < s2;
    });
    auto end = unique(s.begin(), s.end());
    s.erase(end, s.end());
    auto wc = find_if(s.begin(), s.end(), [sz](const string &s1){
        return s1.size() >= sz;
    });
    auto cc = s.end() - wc;
    cout << count << " " << make_plural(cc, "word", "s") << " of length " << sz << " or longer " << endl;
    for_each(wc, s.end(), [](const string &s1){
       cout << s1 << endl; 
    });
}
~~~

### 10.17

~~~C++
sort(v.begin(), v.end(), [](const Sales_data &a, const Sales_data &b){
    return a.isbn().size() < b.isbn().size();
});
~~~

### 10.18 & 10.19

~~~C++
// from ex 10.9
void elimdups(vector<string> &vs)
{
    sort(vs.begin(), vs.end());
    auto new_end = unique(vs.begin(), vs.end());
    vs.erase(new_end, vs.end());
}

// ex10.18
void biggies_partition(vector<string> &vs, size_t sz)
{
    elimdups(vs);
    auto pivot = partition(vs.begin(), vs.end(), [sz](const string &s){
        return s.size() >= sz;}
    );
    for(auto it = vs.cbegin(); it != pivot; ++it)
        std::cout << *it << " ";
}

// ex10.19
void biggies_stable_partition(vector<string> &vs, size_t sz)
{
    elimdups(vs);
    auto pivot = stable_partition(vs.begin(), vs.end(), [sz](const string& s){
        return s.size() >= sz;
    });

    for(auto it = vs.cbegin(); it != pivot; ++it)
        std::cout << *it << " ";
}

int main()
{
    // ex10.18
    vector<string> v{
        "the", "quick", "red", "fox", "jumps", "over", "the", "slow", "red", "turtle"
    };
    
    cout << "ex10.18: ";
    vector<string> v1(v);
    biggies_partition(v1, 4);
    cout << endl;

    // ex10.19
    cout << "ex10.19: ";
    vector<string> v2(v);
    biggies_stable_partition(v2, 4);
    cout << endl;

    return 0;
}
~~~

### 10.20 & 10.21

~~~C++
// 10.20
auto count = count_if(v.begin(), v.end(), [](const string &s){
    return s.size() > 6;
});

// 10.21
int i = 9;
auto what = [i](){return i > 0 ? --i : !i};
~~~

### 10.22

~~~C++
bool isLesserThanOrEqualTo6(const string &s, string::size_type sz)
{
    return s.size() <= sz;
}
sort(v.begin(), v.end(), bind(isLesserThanOrEqualTo6(_1, 6)));
~~~

### 10.23

Assuming the function to be bound have `n` parameters, bind take `n + 1` parameters. The additional one is for the function to be bound itself.

### 10.24

~~~C++
auto check_size(string const& str, size_t sz)
{
    return str.size() < sz;
}

int main()
{
    vector<int> vec{ 0, 1, 2, 3, 4, 5, 6, 7 };
    string str("123456");
    auto result = find_if(vec.begin(), vec.end(), bind(check_size, str, _1));
    if (result != vec.end())
        cout << *result << endl;
    else
        cout << "Not found" << endl;
    return 0;
}
~~~

### 10.25

~~~C++
void elimdups(vector<string> &vs)
{
    sort(vs.begin(), vs.end());
    vs.erase(unique(vs.begin(), vs.end()), vs.end());
}

bool check_size(const string &s, string::size_type sz)
{
    return s.size() >= sz;
}

void biggies(vector<string> &words, vector<string>::size_type sz)
{
    elimdups(words);
    auto iter = stable_partition(words.begin(), words.end(), bind(check_size, _1, sz));
    for_each(words.begin(), iter, [](const string &s){ cout << s << " "; });
}

int main()
{
    vector<string> v{
        "the", "quick", "red", "fox", "jumps", "over", "the", "slow", "red", "turtle"
    };
    biggies(v, 4);
}
~~~

### 10.26

- `back_inserter` uses `push_back`.
- `front_inserter` uses `push_front`.
- `insert` uses `insert`

### 10.27

~~~C++
vector<int> vec{ 1, 1, 3, 3, 5, 5, 7, 7, 9 };
list<int> lst;
unique_copy(vec.begin(), vec.end(), back_inserter(lst));
~~~

### 10.28

~~~C++
template<typename Sequence>
void print(Sequence const& seq)
{
    for (const auto& i : seq)
        cout << i << " ";
    cout << endl;
}

int main()
{
    vector<int> vec{ 1, 2, 3, 4, 5, 6, 7, 8, 9 };
    
    // uses inserter
    list<int> lst1;
    copy(vec.cbegin(), vec.cend(), inserter(lst1, lst1.begin()));
    print(lst1);
    
    // uses back_inserter
    list<int> lit2;
    copy(vec.cbegin(), vec.cend(), back_inserter(lit2));
    print(lit2);
    
    // uses front_inserter
    list<int> lst3;
    copy(vec.cbegin(), vec.cend(), front_inserter(lst3));
    print(lst3);
}
~~~

### 10.29

~~~C++
ifstream fin("D:\\WorkSpace\\C++\\data\\book.txt");
if (!fin)
    cout << "yes" << endl;
istream_iterator<string> in(fin), eof;
vector<string> vec;
copy(in, eof, back_inserter(vec));
copy(vec.cbegin(), vec.cend(), ostream_iterator<string>(cout, "\n"));
~~~

### 10.30

~~~C++
vector<int> vec(istream_iterator<int>(std::cin), istream_iterator<int>());
sort(vec.begin(), vec.end());
copy(vec.cbegin(), vec.cend(), ostream_iterator<int>(cout, " "));
~~~

### 10.31

~~~C++
istream_iterator<int> in_iter(cin), eof;
vector<int> vec;
while (in_iter != eof)
    vec.push_back(*in_iter++);
sort(vec.begin(), vec.end());
unique_copy(vec.cbegin(), vec.cend(), ostream_iterator<int>(cout, " "));
~~~

### 10.32

~~~C++
istream_iterator<Sales_item> in_iter(cin), in_eof;
vector<Sales_item> vec;

while (in_iter != in_eof)
    vec.push_back(*in_iter++);

sort(vec.begin(), vec.end(), compareIsbn);
for (auto beg = vec.cbegin(), end = beg; beg != vec.cend(); beg = end)
{
    end = find_if(beg, vec.cend(), [beg](const Sales_item &item) { return item.isbn() != beg->isbn(); });
    cout << accumulate(beg, end, Sales_item(beg->isbn())) << endl;
}
~~~

### 10.33

~~~C++
int main(int argc, char **argv)
{
    if (argc != 4) return -1;

    ifstream ifs(argv[1]);
    ofstream ofs_odd(argv[2]), ofs_even(argv[3]);

    istream_iterator<int> in(ifs), in_eof;
    ostream_iterator<int> out_odd(ofs_odd, " "), out_even(ofs_even, "\n");

    for_each(in, in_eof, [&out_odd, &out_even](const int i){
        (i & 0x1 ? out_odd : out_even) = i;
    });
    return 0;
}
~~~

### 10.34 ~ 10.37

~~~C++
vector<int> vec = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };

// 10.34
for(auto it = vec.crbegin(); it != vec.crend(); it++)
    cout << *it << endl;

// 10.35
for(auto it = vec.cend();;){
    cout << *(--it) << endl;
    if(it == vec.cbegin())
        break;
}

// 10.36
list<int> lst = { 1, 2, 3, 4, 0, 5, 6 };
auto last = find(lst.crbegin(), lst.crend(), 0);
cout << distance(last, lst.crend());

//10.37
copy(vec.cbegin() + 3, vec.cbegin() + 7, lst.rbegin());
//     0, 1, 2, 3, 4, 5, 6, 7, 8, 9
//           ^              ^
//          rend          rbegin
// @note: std::copy copies the range [first, last) into result.
//        hence, the arguments here denote:
//        [7 6 5 4 3 2)
//                   ^ this one is specified but not included.
~~~

### 10.38

- Input iterators : `==`, `!=`, `++`, `*`, `->`
- Output iterators : `++`, `*`
- Forward iterators : `==`, `!=`, `++`, `*`, `->`
- Bidirectional iterators : `==`, `!=`, `++`, `--`, `*`, `->`
- Random-access iterators : `==`, `!=`, `<`, `<=`, `>`, `>=`, `++`, `--`, `+`, `+=`, `-`, `-=`, `-`(two iterators), `*`, `->`, `iter[n]` == `* (iter + n)`

### 10.39

`list` have the **Bidirectional iterators**. 

`vector` have the **Random-access iterators**.

### 10.40

- `copy` : first and second are Input iterators, last is Output iterators.
- `reverse` : Bidirectional iterators.
- `unique` : Forward iterators.

### 10.41

~~~C++
replace(beg, end, old_val, new_val); // replace the old_elements in the input range as new_elements.
replace_if(beg, end, pred, new_val); // replace the elements in the input range which pred is true as new_elements.
replace_copy(beg, end, dest, old_val, new_val); // copy the new_elements which is old_elements in the input range into dest.
replace_copy_if(beg, end, dest, pred, new_val); // copy the new_elements which pred is true in the input range into dest.
~~~

### 10.42

~~~C++
void elimDups(list<string> &words)
{
    words.sort();
    words.unique();
}

int main()
{
    list<string> l = { "aa", "aa", "aa", "aa", "aasss", "aa" };
    elimDups(l);
    for (const auto& e : l)
        cout << e << " ";
    cout << endl;
}
~~~

## 第十一章

### 11.1

`map` : 关联容器，元素根据键值对存储和检索，二叉搜索树实现

`vector` :  顺序容器，元素按其在容器中的位置顺序存储和访问，动态数组实现

### 11.2

`list` : 不需要随机访问数据，但希望在容器的任何位置(例如内存管理分配器中)快速插入或删除数据。

`vector` : 连续存储和处理一组数据时，支持随机访问和末尾的快速插入和删除。

`deque` : FIFO。

`map` : 将相关信息配对时使用映射，需要在大量数据中查找pair时。

`set` : 创建一个有序对象的列表(树)，以便快速遍历/搜索时。

### 11.3

~~~C++
void fun(map<string, size_t> &mp, vector<string> words)
{
    for(auto s:words)
        ++mp[s];
}
~~~

### 11.4

~~~C++
auto strip(string& str) -> string const&
{
    for (auto& ch : str) ch = tolower(ch);
    str.erase(remove_if(str.begin(), str.end(), ispunct), str.end());
    return str;
}
void fun(map<string, size_t> &mp, vector<string> words)
{
    for(auto s:words)
        ++mp[strip(s)];
}
~~~

### 11.5

[map vs set](https://stackoverflow.com/questions/16286714/advantages-of-stdset-vs-vectors-or-maps)

形成字符串有序集就直接用 `set` ，如果还想知道每个字符的含义，比如出现次数，就用 `map`

### 11.6

[list vs set](https://stackoverflow.com/questions/2302681/c-stl-list-vs-set)

`set` 单一有序，`list` 可重复无序

### 11.7

~~~C++
using Families = map<string, vector<string>>;

auto make_families()
{
    Families families;
    for (string ln; cout << "Last name:\n", cin >> ln && ln != "@q";)
        for (string cn; cout << "|-Children's names:\n", cin >> cn && cn != "@q";)
            families[ln].push_back(cn);
    return families;
}

auto print(Families const& families)
{
    for (auto const& family : families)
    {
        cout << family.first << ":\n";
        for (auto const& child : family.second)
            cout << child << " ";
        cout << "\n";
    }
}

int main()
{
    print(make_families());
    return 0;
}
~~~

### 11.8

~~~C++
int main()
{
    vector<string> exclude = { "aa", "bb", "cc", "dd", "ee", "ff" };
    for (string word; cout << "Enter plz:\n", cin >> word; )
    {
        auto is_excluded = binary_search(exclude.cbegin(), exclude.cend(), word);
        auto reply = is_excluded ? "excluded" : "not excluded";
        cout << reply << endl;
    }
    return 0;
}
~~~

### 11.9 & 11.10

~~~C++
// 11.9
map<string, list<size_t>> mp;

// 11.10
map<vector<int>::iterator, int> mvt;
map<list<int>::iterator, int> mlt;

vector<int> vi;
mv.insert(pair<vector<int>::iterator, int>(vi.begin(), 0));

// but when using this one the compiler complained that
// error: no match for 'operator<' in '__x < __y'

list<int> li;
ml.insert(pair<list<int>::iterator, int>(li.begin(), 0));
~~~

### 11.11

~~~C++
#include "../ch07/ex7_26.h"
#include <set>

auto less(Sales_data const& lhs, Sales_data const& rhs)
{
    return lhs.isbn() < rhs.isbn();
}

int main()
{
    using Less = bool (*)(Sales_data const&, Sales_data const&);
    multiset<Sales_data, Less> bookstore(less);

    return 0;
}
~~~

### 11.12 & 11.13

~~~C++
vector<pair<string, int>> vec;
void fun(vector<string> &s, vector<int> &a){
    for(int i = 0; i<s.size() && i < a.size();i++)
        vec.push_back({s[i],a[i]});
        //vec.push_back(pair<string, int>(str, i));
        //vec.push_back(make_pair(str, i));
        //vec.emplace_back(str, i); //easiest way.
}
~~~

### 11.14

~~~C++
class Families
{
public:
    using Child     = pair<string, string>;
    using Children  = vector<Child>;
    using Data      = map<string, Children>;

    auto add(string const& last_name, string const& first_name, string birthday)
    {
        auto child = make_pair(first_name, birthday);
        _data[last_name].push_back(child);
    }

    auto print() const
    {
        for (auto const& pair : _data)
        {
            cout << pair.first << ":\n" ;
            for (auto const& child : pair.second)
                cout << child.first << " " << child.second << endl;
            cout << endl;
        }
    }

private:
    Data _data;
};

int main()
{
    Families families;
    auto msg = "Please enter last name, first name and birthday:\n";
    for (string l, f, b; cout << msg, cin >> l >> f >> b; families.add(l, f, b));
    families.print();

    return 0;
}
~~~

### 11.15

~~~C++
map<int, vector<int>> mp;
// key_type : int
// mapped_type : vector<int>
// value_type : pair<int, vector<int>>
~~~

### 11.16

~~~C++
map<int, string> mp;
mp[1] = "hello";
auto it = mp.cbegin();
string s = it->second;
~~~

### 11.17

~~~C++
muliset<string> c;
vector<string> v;
copy(v.begin(), v.end(), inserter(c, c.end())); // legal
copy(v.begin(), v.end(), back_inserter(c)); // illegal, no `push_back` in `set`.
copy(c.begin(), c.end(), inserter(v, v.end())); // legal.
copy(c.begin(), c.end(), back_inserter(v)); // legal.
~~~

### 11.18

`map<string, size_t>::const_iterator`

### 11.19

~~~C++
using compareType = bool (*)(const Sales_data &lhs, const Sales_data &rhs);
multiset<Sales_data, compareType> bookstore(compareIsbn);
multiset<Sales_data, compareType>::iterator c_it = bookstore.begin();
~~~

### 11.20

~~~C++
map<string, size_t> counts;
for(string word; cin >> word;)
{
    auto result = counts.insert({ word, 1 });
    if(!result.second)
        ++result.first->second;
}
for(auto const& count : counts)
    cout << count.first << " " << count.second << ((count.second > 1) ? " times\n" : " time\n");
~~~

### 11.21

~~~C++
map<string, size_t> word_count;
string word;
while(cin >> word)
    ++word_count.insert({word, 0}).first->second; // 计数
~~~

### 11.22

`map<string, int>`

`pair<map<string, vector<int>>, bool>`

### 11.23

~~~C++
int main()
{
    multimap<string, string> families;
    for (string lname, cname; cin >> cname >> lname; families.emplace(lname, cname));
    for (auto const& family : families)
        cout << family.second << " " << family.first << endl;
}
~~~

### 11.24 ~ 11.26

~~~C++
// 11.24
// 建立0-1对
map<int, int> m;
m[0] = 1;

// 11.25
// 超范围了
vector<int> v;
v[0] = 1;

// 11.26
map<int, string> m = { { 1,"ss" },{ 2,"sz" } };
using KeyType = map<int, string>::key_type;

cout << "type to subscript: " << typeid(KeyType).name() << endl;
cout << "returned from the subscript operator: " << typeid(decltype(m[1])).name();
~~~

### 11.27 ~ 11.30

~~~C++
// 11.27
// multi用count, 有唯一键的直接用find

// 11.28
map<string, vector<int>> mp;
auto it = mp.find(name);

// 11.29
// upper_bound == lower_bound, equal_range
// 如果没有找到匹配的元素，则first和second迭代器指向这个键可以的位置插入。

// 11.30
pos; // pair
pos.first; // 迭代器
pos.first->second; // 这个作者的某本书 
~~~

### 11.31

~~~C++
multimap<string, string> authors{
    { "alan", "DMA" },
    { "pezy", "LeetCode" },
    { "alan", "CLRS" },
    { "wang", "FTP" },
    { "pezy", "CP5" },
    { "wang", "CPP-Concurrency" }
};
string author = "pezy";
string work = "CP5";

auto found = authors.find(author);
auto count = authors.count(author);
while (count) {
    if (found->second == work) {
        authors.erase(found);
        break;   
    }
    ++found;
    --count;
}

for (const auto &author : authors)
    std::cout << author.first << " " << author.second << std::endl;
~~~

### 11.32

~~~C++
multimap<string, string> authors{
    { "alan", "DMA" },
    { "pezy", "LeetCode" },
    { "alan", "CLRS" },
    { "wang", "FTP" },
    { "pezy", "CP5" },
    { "wang", "CPP-Concurrency" }
};
map<string, multiset<string>> order_authors;
for (const auto &author : authors)
    order_authors[author.first].insert(author.second);
for (const auto &author : order_authors) {
    cout << author.first << ": ";
    for (const auto &work : author.second)
        cout << work << " ";
    cout << endl;
}
~~~

### 11.33

~~~C++
#include <bits/stdc++.h>
using namespace std;

map<string, string> buildMap(ifstream &map_file)
{
    map<string, string> trans_map;
    for (string key, value; map_file >> key && getline(map_file, value); )
        if (value.size() > 1) trans_map[key] = value.substr(1).substr(0, value.find_last_not_of(' '));
    return trans_map;
}

const string & transform(const string &s, const map<string, string> &m)
{
    auto map_it = m.find(s);
    return map_it == m.cend() ? s : map_it->second;
}

void word_transform(ifstream &map, ifstream &input)
{
    auto trans_map = buildMap(map);
    for (string text; getline(input, text); ) {
        istringstream iss(text);
        for (string word; iss >> word; )
            cout << transform(word, trans_map) << " ";
        cout << endl;
    }
}

int main()
{
    ifstream ifs_map("../data/word_transformation_bad.txt");
    ifstream ifs_content("../data/given_to_transform.txt");
    if (ifs_map && ifs_content) word_transform(ifs_map, ifs_content);
    else cerr << "can't find the documents." << endl;
}
~~~

### 11.34

可能会创建原先不存在的键值对

### 11.35

- use subscript operator: if a word does appear multiple times, our loops will put the **last** corresponding phrase into trans_map
- use `insert`: if a word does appear multiple times, our loops will put the **first** corresponding phrase into trans_map

### 11.36

不会被替换，因为替换规则首先得满足 `value.size() > 1`

### 11.37

- Ordered Associative Container

- - Standard Traversal encounters elements in sorted order
    - Order predicate may be specified
    - Default order predicate is "less than", defined using operator< for the element type
    - Popular implementations: OrderedVector, BinarySearchTree
    - Search operations required to have O(log *n*) runtime
    - Insert, Remove operations should either be seldom used or have O(log *n*) runtime

- Unordered Associative Container

- - Standard Traversal encounters elements in unspecified order
    - Search, Insert, Remove operations should have average-case constant runtime
    - Popular implementations use hashing

### 11.38

~~~C++
void wordCounting()
{
    unordered_map<string, size_t> word_count;
    for (string word; cin >> word; ++word_count[word]);
    for (const auto &w : word_count)
        cout << w.first << " occurs " << w.second << (w.second > 1 ? "times" : "time") << endl;
}

void wordTransformation()
{
    ifstream ifs_map("../data/word_transformation.txt");
    ifstream ifs_content("../data/given_to_transform.txt");
    if (!ifs_map || !ifs_content) {
        cerr << "can't find the documents." << endl;
        return;
    }
    
    unordered_map<string, string> trans_map;
    for (string key, value; ifs_map >> key && getline(ifs_map, value); )
        if (value.size() > 1) 
            trans_map[key] = value.substr(1).substr(0, value.find_last_not_of(' '));
    
    for (string text, word; getline(ifs_content, text); cout << endl)
        for (istringstream iss(text); iss >> word; ) {
            auto map_it = trans_map.find(word);
            cout << (map_it == trans_map.cend() ? word : map_it->second) << " ";
        }
}

int main()
{
    //wordCounting();
    wordTransformation();
}
~~~

## 第十二章

### 12.1

~~~C++
StrBlob b1
{
    StrBlob b2 = {"a", "an", "the"};
    b1 = b2;
    b2.push_back("about");
}
// b1 有四个, b2自动销毁了
~~~

### 12.2

~~~C++
class StrBlob 
{
public:
    using size_type = vector<string>::size_type;

    StrBlob():data(make_shared<vector<string>>()) { }
    StrBlob(initializer_list<string> il):data(make_shared<vector<string>>(il)) { }

    size_type size() const { return data->size(); }
    bool empty() const { return data->empty(); }

    void push_back(const string &t) { data->push_back(t); }
    void pop_back() {
        check(0, "pop_back on empty StrBlob");
        data->pop_back();
    }

    string& front() 
    {
        check(0, "front on empty StrBlob");
        return data->front();
    }

    string& back() 
    {
        check(0, "back on empty StrBlob");
        return data->back();
    }

    const string& front() const 
    {
        check(0, "front on empty StrBlob");
        return data->front();
    }
    const string& back() const 
    {
        check(0, "back on empty StrBlob");
        return data->back();
    }

private:
    void check(size_type i, const string &msg) const 
    {
        if (i >= data->size()) throw out_of_range(msg);
    }

private:
    shared_ptr<vector<string>> data;
};
~~~

### 12.3

[可以但没必要](https://stackoverflow.com/questions/20725190/operating-on-dynamic-memory-is-it-meaningful-to-overload-a-const-memeber-functi)

### 12.4

`i` 是 `unsigned` 的

### 12.5

**Pros**

- The compiler will not use this constructor **in an automatic conversion**.
- We can realize clearly which class we have used.

**Cons**

- We always uses the constructor to construct **a temporary StrBlob object**.
- cannot use the copy form of initialization with an explicit constructor. not easy to use.

### 12.6

~~~C++
auto fun()
{
    return new vector<int>{};
}

auto read(vector<int>* vec)
{
    for(int i; cin >> i; vec->push_back(i));
    return vec;
}

void print(vector<int>* vec)
{
    for(auto i : *vec)
        cout << i <<" ";
    delete vec;
}

int main()
{
    print(read(fun));
    return 0;
}
~~~

### 12.7

~~~C++
auto fun()
{
    return make_shared<vector<int>>();
}

auto read(share_ptr<vector<int>> vec)
{
    for(int i; cin >> i; vec->push_back(i));
    return vec;
}

void print(share_ptr<vector<int>> vec)
{
    for(auto i : *vec)
        cout << i <<" ";
}

int main()
{
    print(read(fun));
    return 0;
}
~~~

### 12.8

~~~C++
bool b()
{
    int* p = new int;
    return p;
} // 内存泄漏
~~~

### 12.9

~~~C++
int *q = new int(42), *r = new int(100);
r = q; // 100的内存没有释放
auto q2 = make_shared<int>(42), r2 = make_shared<int>(100);
r2 = q2; // 100的内存在计数器为0的情况下自动回收
~~~

### 12.10

~~~C++
// 可以
void process(shared_ptr<int> ptr)
{
    cout << "inside the process function:" << ptr.use_count() << "\n";
}

int main()
{
    shared_ptr<int> p(new int(42));
    process(shared_ptr<int>(p));
    cout << p.use_count() << "\n" << *p << "\n";
    return 0;
}
~~~

### 12.11

函数内部可能会将 `p` 指向的内存释放，避免这种写法

### 12.12

~~~C++
void process(shared_ptr<int> ptr)
{
    cout << "inside the process function:" << ptr.use_count() << "\n";
}

int main()
{
    auto p = new int();
    auto sp = make_shared<int>();

    process(sp); // 可以
    process(new int()); // 不允许隐式转换
    process(p); // 同上
    process(std::shared_ptr<int>(p)); // 可以，但最好别这么写，因为可能会用到非法指针p

    return 0;
}
~~~

### 12.13

~~~C++
auto sp = make_shared<int>();
auto p = sp.get();
delete p;
~~~

### 12.14

~~~C++
#include <bits/stdc++.h>
using namespace std;

struct connection {
    string ip;
    int port;
    connection(string ip_, int port_):ip(ip_), port(port_){ }
};
struct destination {
    string ip;
    int port;
    destination(string ip_, int port_):ip(ip_), port(port_){ }
};

connection connect(destination* pDest)
{
    shared_ptr<connection> pConn(new connection(pDest->ip, pDest->port));
    cout << "creating connection(" << pConn.use_count() << ")" << endl;
    return *pConn;
}

void disconnect(connection pConn)
{
    cout << "connection close(" << pConn.ip << ":" << pConn.port << ")" << endl;
}

void end_connection(connection *pConn)
{
    disconnect(*pConn);
}

void f(destination &d)
{
    connection conn = connect(&d);
    shared_ptr<connection> p(&conn, end_connection);
    cout << "connecting now(" << p.use_count() << ")" << endl;
}

int main()
{
    destination dest("202.118.176.67", 3316);
    f(dest);
}
~~~

### 12.15

~~~C++
shared_ptr<connection> p(&conn, [](connection *pConn){
    disconnect(*pConn);
});
~~~

### 12.16

~~~C++
#include <iostream>
#include <string>
#include <memory>

using std::string; using std::unique_ptr;

int main()
{
    unique_ptr<string> p1(new string("string"));
    // unique_ptr<string> p2(p1); // copy
    //                      ^
    // Error: Call to implicitly-deleted copy constructor of 'unique_ptr<string>'
    //
    // unique_ptr<string> p3 = p1; // assign
    //                      ^
    // Error: Call to implicitly-deleted copy constructor of 'unique_ptr<string>'
    std::cout << *p1 << std::endl;
    p1.reset(nullptr);
}
~~~

### 12.17 & 12.18

~~~C++
#include <iostream>
#include <vector>
#include <string>
#include <memory>


int main()
{
    int ix = 1024, *pi = &ix, *pi2 = new int(2048);
    typedef std::unique_ptr<int> IntP;


    /**
     * @brief  error: invalid conversion from 'int' to 'std::unique_ptr<int>::pointer { aka int* }' [-fpermissive]
     */
    //IntP p0(ix);


    /**
     * @brief The code below can compile, but will cause error at run time.
     *        The reason is that when the unique_ptr p1 is out of scope, delete will be called
     *        to free th object. But the object is not allocate using new.Thus, an error
     *        would be thrown by operating system.
     *  @badcode
     */
    //IntP p1(pi);


    /**
     * @brief This code can compile, but cause a dangling pointer at run time.
     *        The reason is that the unique_ptr will free the object the raw pointer
     *        is pointing to.
     * @badcode
     */
    //{ IntP p2(pi2); }


    /**
     * @brief   When the unique_ptr goes out of scope, it will call delete to free an
     *          obeject not allocated using new.
     * @badcode
     */
    //IntP p3(&ix);


    /**
     * @brief   Recommended.
     */
    //IntP p4(new int(2048));


    /**
     * @brief   error:   double free or corruption at run time
     *          two unique_ptr are pointing to the same object. Thus, when both are out of
     *          scope, Operating system will throw double free or corruption.
     * @badcode
     */
    //IntP p2(new int(555));
    //IntP p5(p2.get());

    return 0;
}

// 	Exercise 12.18:
// 	Why doesn’t shared_ptr have a release member?
//  	Because other shared_ptr that points the same object can still delete this
//  	object.Thus, it's meaningless to provide this member
//  	more detail can be found a thread on Stack Overflow:
// 		http://stackoverflow.com/questions/1525764/how-to-release-pointer-from-boostshared-ptr
~~~

### 12.19

~~~C++
class StrBlobPtr;

class StrBlob
{
public:
    using size_type = vector<string>::size_type;
    friend class StrBlobPtr;

    StrBlobPtr begin();
    StrBlobPtr end();

    StrBlob() : data(std::make_shared<vector<string>>()) {}
    StrBlob(std::initializer_list<string> il) : data(std::make_shared<vector<string>>(il)) {}

    size_type size() const { return data->size(); }
    bool empty() const { return data->empty(); }

    void push_back(const string &t) { data->push_back(t); }
    void pop_back()
    {
        check(0, "pop_back on empty StrBlob");
        data->pop_back();
    }

    std::string &front()
    {
        check(0, "front on empty StrBlob");
        return data->front();
    }

    std::string &back()
    {
        check(0, "back on empty StrBlob");
        return data->back();
    }

    const std::string &front() const
    {
        check(0, "front on empty StrBlob");
        return data->front();
    }
    const std::string &back() const
    {
        check(0, "back on empty StrBlob");
        return data->back();
    }

private:
    void check(size_type i, const string &msg) const
    {
        if (i >= data->size())
            throw std::out_of_range(msg);
    }

private:
    std::shared_ptr<vector<string>> data;
};

class StrBlobPtr
{
public:
    StrBlobPtr() : curr(0) {}
    StrBlobPtr(StrBlob &a, size_t sz = 0) : wptr(a.data), curr(sz) {}
    bool operator!=(const StrBlobPtr &p) { return p.curr != curr; }
    string &deref() const
    {
        auto p = check(curr, "dereference past end");
        return (*p)[curr];
    }
    StrBlobPtr &incr()
    {
        check(curr, "increment past end of StrBlobPtr");
        ++curr;
        return *this;
    }

private:
    std::shared_ptr<vector<string>> check(size_t i, const string &msg) const
    {
        auto ret = wptr.lock();
        if (!ret)
            throw std::runtime_error("unbound StrBlobPtr");
        if (i >= ret->size())
            throw std::out_of_range(msg);
        return ret;
    }
    std::weak_ptr<vector<string>> wptr;
    size_t curr;
};

StrBlobPtr StrBlob::begin()
{
    return StrBlobPtr(*this);
}

StrBlobPtr StrBlob::end()
{
    return StrBlobPtr(*this, data->size());
}
~~~

### 12.20

~~~C++
int main()
{
    ifstream ifs("../data/book.txt");
    StrBlob blob;
    for(string str;getline(ifs,str);)
        blob.push_back(str);
    for(StrBlobPtr pbeg(blob.begin()), pend(blob.end()); pbeg != pend; pbeg.incr())
        cout << pbeg.deref() <<endl;
}
~~~

### 12.21

这样写不好读，还是原版好

### 12.22

~~~C++
// 思路就是常对象调用常函数，所以会被调用的函数都改成常函数

class ConstStrBlobPtr
{
public:
    ConstStrBlobPtr() : curr(0) {}
    ConstStrBlobPtr(const StrBlob &a, size_t sz = 0) : wptr(a.data), curr(sz) {} // should add const
    bool operator!=(ConstStrBlobPtr &p) { return p.curr != curr; }
    const string &deref() const
    { // return value should add const
        auto p = check(curr, "dereference past end");
        return (*p)[curr];
    }
    ConstStrBlobPtr &incr()
    {
        check(curr, "increment past end of StrBlobPtr");
        ++curr;
        return *this;
    }

private:
    std::shared_ptr<vector<string>> check(size_t i, const string &msg) const
    {
        auto ret = wptr.lock();
        if (!ret)
            throw std::runtime_error("unbound StrBlobPtr");
        if (i >= ret->size())
            throw std::out_of_range(msg);
        return ret;
    }
    std::weak_ptr<vector<string>> wptr;
    size_t curr;
};

ConstStrBlobPtr StrBlob::begin() const // should add const
{
    return ConstStrBlobPtr(*this);
}

ConstStrBlobPtr StrBlob::end() const // should add const
{
    return ConstStrBlobPtr(*this, data->size());
}

// and should add something into the class StrBlob
class ConstStrBlobPtr;
class StrBlob
{
    //...
    friend class ConstStrBlobPtr;

    ConstStrBlobPtr begin() const; // should add const
    ConstStrBlobPtr end() const;   // should add const
    //...
}
~~~

### 12.23

~~~C++
#include <string.h>
#include <iostream>
#include <string>
using namespace std;
int main()
{
    char s1[] = "hello,";
    char s2[] = "world!";
    char *s = new char[strlen(s1) + strlen(s2) + 1]();
    strcat(s, s1);
    strcat(s, s2);
    cout << s << endl;
	delete[] s;
    s = nullptr;
    
    // string
    string str1("hello,"), str2("world!");
    cout << str1 + str2 << endl;

    return 0;
}
~~~

### 12.24

~~~C++
// 使用空白字符分隔
#include <iostream>
#include <string>
#include <cstring>
using namespace std;
char *charUp(char *p, const size_t &oldSize, const size_t &newSize)
{
    char *newBlock = new char[newSize]();
    if (!p)
        return newBlock;
    memcpy(newBlock, p, oldSize);
    delete[] p;
    p = newBlock;
    return p;
}
int main()
{
    char ch, *str = nullptr;
    constexpr size_t sizeSt = 24;
    size_t i = 0, length = 0;
    while (cin >> ch >> noskipws && !isspace(ch))
    {
        if (i == length)
        {
            length += sizeSt;
            str = charUp(str, i, length);
            if (!str)
            {
                cout << "Could not allocate memory!" << endl;
                return -1;
            }
        }
        str[i++] = ch;
    }
    str[i] = '\0';
    cout << string(str) << endl;
    delete[] str;
    str = nullptr;
    return 0;
}
~~~

### 12.25

~~~C++
delete[] pa;
~~~

### 12.26

~~~C++
#include <iostream>
#include <string>
#include <cstring>
#include <memory>
using namespace std;
const int n = 5;
int main()
{
    allocator<string> a;
    auto const p = a.allocate(n);
    string s;
    auto q = p;
    while (q != p + n && cin >> s)
        a.construct(q++, s);
    int count = 0;
    while (q != p)
    {
        count++;
        cout << *--q << endl;
        a.destroy(q);
    }
    a.deallocate(p, n);
    cout << count << endl;
    return 0;
}
~~~

### 12.27 & 12.30

~~~C++
#include <iostream>
#include <string>
#include <vector>
#include <map>
#include <set>
#include <memory>
#include <sstream>
#include <algorithm>
#include <fstream>
#include <ctype.h>
using namespace std;

class QueryResult;
class TextQuery
{
public:
    using LineNo = vector<string>::size_type;
    TextQuery(ifstream &);
    QueryResult query(const string &) const;

private:
    shared_ptr<vector<string>> input;
    map<string, shared_ptr<set<LineNo>>> result;
};

class QueryResult
{
public:
    friend ostream &print(ostream &, const QueryResult &);
    QueryResult(string s, shared_ptr<set<TextQuery::LineNo>> ns, shared_ptr<vector<string>> in) : word(s), nos(ns), input(in){};

private:
    string word;
    shared_ptr<set<TextQuery::LineNo>> nos;
    shared_ptr<vector<string>> input;
};

TextQuery::TextQuery(ifstream &infile) : input(new vector<string>)
{
    LineNo lineNo{0};
    for (string line; getline(infile, line); lineNo++)
    {
        input->push_back(line);
        istringstream s_line(line);
        for (string text, word; s_line >> text; word.clear())
        {
            // avoid "word, "
            remove_copy_if(text.begin(), text.end(), back_inserter(word), ptr_fun<int, int>(&std::ispunct));
            auto &nos = result[word];
            if (!nos)
                nos.reset(new set<LineNo>);
            nos->insert(lineNo);
        }
    }
}

QueryResult TextQuery::query(const string &str) const
{
    // use static just allocate once
    static shared_ptr<set<LineNo>> nodata(new set<LineNo>);
    auto found = result.find(str);
    if (found == result.end())
        return QueryResult(str, nodata, input);
    else
        return QueryResult(str, found->second, input);
}

ostream &print(ostream &out, const QueryResult &qr)
{
    out << qr.word << " occurt: " << qr.nos->size() << " " << (qr.nos->size() > 1 ? "times" : "time") << endl;
    for (auto i : *qr.nos)
        cout << "\t(line " << i + 1 << ") " << qr.input->at(i) << endl;
    return out;
}

void runQuery(ifstream &infile)
{
    TextQuery tq(infile);
    while (1)
    {
        cout << "Please input a word to look for, or 'q' to quit\n";
        string s;
        if (!(cin >> s) || s == "q")
            break;
        print(cout, tq.query(s)) << endl;
    }
}

int main()
{
    ifstream ifs("D:/WorkSpace/C++/data.txt");
    runQuery(ifs);

    return 0;
}
~~~

### 12.28

~~~C++
#include <iostream>
#include <string>
#include <vector>
#include <map>
#include <set>
#include <memory>
#include <sstream>
#include <algorithm>
#include <fstream>
#include <ctype.h>
using namespace std;

int main()
{
    ifstream ifs("D:/WorkSpace/C++/data.txt");
    vector<string> input;
    map<string, set<decltype(input.size())>> dict;
    decltype(input.size()) lineNo{0};

    for (string line; getline(ifs, line); lineNo++)
    {
        input.push_back(line);
        istringstream s_line(line);
        for (string text, word; s_line >> text; word.clear())
        {
            // avoid "word, "
            remove_copy_if(text.begin(), text.end(), back_inserter(word), ptr_fun<int, int>(&std::ispunct));
            dict[word].insert(lineNo);
        }
    }

    while (1)
    {
        cout << "Please input a word to look for, or 'q' to quit\n";
        string s;
        if (!(cin >> s) || s == "q")
            break;

        auto found = dict.find(s);
        if (found == dict.end())
            cout << s << " occurt: " << 0 << " "
                 << "time" << endl;
        else
        {
            cout << s << " occurt: " << found->second.size() << " " << (found->second.size() > 1 ? "times" : "time") << endl;
            for (auto i : found->second)
                cout << "\t(line " << i + 1 << ") " << input.at(i) << endl;
        }

        cout << endl;
    }
    return 0;
}
~~~

### 12.29

~~~C++
// In terms of narrative order, I perfer do while
do{
    cout << "Please input a word to look for, or 'q' to quit\n";
    string s;
    if (!(cin >> s) || s == "q")
        break;
    print(cout, tq.query(s)) << endl;
}while (1);
~~~

### 12.31

vector代替set后，同一行多次出现的单词会重复进入存储空间，使用set能使得序列中同一元素唯一

### 12.32

~~~C++
#include <iostream>
#include <string>
#include <vector>
#include <map>
#include <set>
#include <memory>
#include <sstream>
#include <algorithm>
#include <fstream>
#include <ctype.h>
using namespace std;

class ConstStrBlobPtr;
class StrBlobPtr;

class StrBlob
{
public:
    using size_type = vector<string>::size_type;
    friend class StrBlobPtr;
    friend class ConstStrBlobPtr;

    ConstStrBlobPtr begin() const; // should add const
    ConstStrBlobPtr end() const;   // should add const

    StrBlobPtr begin();
    StrBlobPtr end();

    StrBlob() : data(std::make_shared<vector<string>>()) {}
    StrBlob(std::initializer_list<string> il) : data(std::make_shared<vector<string>>(il)) {}

    size_type size() const { return data->size(); }
    bool empty() const { return data->empty(); }

    void push_back(const string &t) { data->push_back(t); }
    void pop_back()
    {
        check(0, "pop_back on empty StrBlob");
        data->pop_back();
    }

    std::string &front()
    {
        check(0, "front on empty StrBlob");
        return data->front();
    }

    std::string &back()
    {
        check(0, "back on empty StrBlob");
        return data->back();
    }

    const std::string &front() const
    {
        check(0, "front on empty StrBlob");
        return data->front();
    }
    const std::string &back() const
    {
        check(0, "back on empty StrBlob");
        return data->back();
    }

private:
    void check(size_type i, const string &msg) const
    {
        if (i >= data->size())
            throw std::out_of_range(msg);
    }

private:
    std::shared_ptr<vector<string>> data;
};

class StrBlobPtr
{
public:
    StrBlobPtr() : curr(0) {}
    StrBlobPtr(StrBlob &a, size_t sz = 0) : wptr(a.data), curr(sz) {}
    bool operator!=(const StrBlobPtr &p) { return p.curr != curr; }
    string &deref() const
    {
        auto p = check(curr, "dereference past end");
        return (*p)[curr];
    }
    StrBlobPtr &incr()
    {
        check(curr, "increment past end of StrBlobPtr");
        ++curr;
        return *this;
    }

private:
    std::shared_ptr<vector<string>> check(size_t i, const string &msg) const
    {
        auto ret = wptr.lock();
        if (!ret)
            throw std::runtime_error("unbound StrBlobPtr");
        if (i >= ret->size())
            throw std::out_of_range(msg);
        return ret;
    }
    std::weak_ptr<vector<string>> wptr;
    size_t curr;
};

class ConstStrBlobPtr
{
public:
    ConstStrBlobPtr() : curr(0) {}
    ConstStrBlobPtr(const StrBlob &a, size_t sz = 0) : wptr(a.data), curr(sz) {} // should add const
    bool operator!=(ConstStrBlobPtr &p) { return p.curr != curr; }
    const string &deref() const
    { // return value should add const
        auto p = check(curr, "dereference past end");
        return (*p)[curr];
    }
    ConstStrBlobPtr &incr()
    {
        check(curr, "increment past end of StrBlobPtr");
        ++curr;
        return *this;
    }

private:
    std::shared_ptr<vector<string>> check(size_t i, const string &msg) const
    {
        auto ret = wptr.lock();
        if (!ret)
            throw std::runtime_error("unbound StrBlobPtr");
        if (i >= ret->size())
            throw std::out_of_range(msg);
        return ret;
    }
    std::weak_ptr<vector<string>> wptr;
    size_t curr;
};

StrBlobPtr StrBlob::begin()
{
    return StrBlobPtr(*this);
}

StrBlobPtr StrBlob::end()
{
    return StrBlobPtr(*this, data->size());
}

ConstStrBlobPtr StrBlob::begin() const // should add const
{
    return ConstStrBlobPtr(*this);
}

ConstStrBlobPtr StrBlob::end() const // should add const
{
    return ConstStrBlobPtr(*this, data->size());
}

class QueryResult;
class TextQuery
{
public:
    TextQuery(ifstream &);
    QueryResult query(const string &) const;

private:
    StrBlob input;
    map<string, shared_ptr<set<StrBlob::size_type>>> result;
};

class QueryResult
{
public:
    friend ostream &print(ostream &, const QueryResult &);
    QueryResult(const string &s, shared_ptr<set<StrBlob::size_type>> ns, const StrBlob &in) : word(s), nos(ns), input(in){};

private:
    string word;
    shared_ptr<set<StrBlob::size_type>> nos;
    StrBlob input;
};

TextQuery::TextQuery(ifstream &infile)
{
    StrBlob::size_type lineNo{0};
    for (string line; getline(infile, line); ++lineNo)
    {
        input.push_back(line);
        istringstream s_line(line);
        for (string text, word; s_line >> text; word.clear())
        {
            // avoid "word, "
            remove_copy_if(text.begin(), text.end(), back_inserter(word), ptr_fun<int, int>(&std::ispunct));
            auto &nos = result[word];
            if (!nos)
                nos.reset(new set<StrBlob::size_type>);
            nos->insert(lineNo);
        }
    }
}

QueryResult TextQuery::query(const string &str) const
{
    // use static just allocate once
    static shared_ptr<set<StrBlob::size_type>> nodata(new set<StrBlob::size_type>);
    auto found = result.find(str);
    if (found == result.end())
        return QueryResult(str, nodata, input);
    else
        return QueryResult(str, found->second, input);
}

ostream &print(ostream &out, const QueryResult &qr)
{
    out << qr.word << " occurt: " << qr.nos->size() << " " << (qr.nos->size() > 1 ? "times" : "time") << endl;
    for (auto i : *qr.nos)
    {
        ConstStrBlobPtr p(qr.input, i);
        cout
            << "\t(line " << i + 1 << ") " << p.deref() << endl;
    }
    return out;
}

void runQuery(ifstream &infile)
{
    TextQuery tq(infile);
    while (1)
    {
        cout << "Please input a word to look for, or 'q' to quit\n";
        string s;
        if (!(cin >> s) || s == "q")
            break;
        print(cout, tq.query(s)) << endl;
    }
}

int main()
{
    ifstream ifs("D:/WorkSpace/C++/data.txt");
    runQuery(ifs);

    return 0;
}
~~~

### 12.33

~~~C++
class QueryResult
{
    using ResultIter = set<StrBlob::size_type>::iterator;

public:
    friend ostream &print(ostream &, const QueryResult &);
    QueryResult(const string &s, shared_ptr<set<StrBlob::size_type>> ns, const StrBlob &in) : word(s), nos(ns), input(in){};
    ResultIter begin() const { return nos->begin(); }
    ResultIter end() const { return nos->end(); }
    shared_ptr<StrBlob> get_file() const { return make_shared<StrBlob>(input); }

private:
    string word;
    shared_ptr<set<StrBlob::size_type>> nos;
    StrBlob input;
};
~~~

## 第十三章

### 13.1

拷贝构造函数是第一个参数是当前类的引用，其它参数都有默认值的函数

当拷贝初始化发生：

- 使用 `=` 定义一个变量
- 将对象作为参数传给非引用类型形参
- 从非引用类型返回值的函数返回对象
- 用花括号列表（List Initialization）初始化聚合类的成员或者数组中的元素
- 某些类类型还会为所分配的对象使用拷贝初始化

### 13.2

~~~C++
Sales_data::Sales_data(Sales_data rhs);
// Infinite loop
~~~

### 13.3

~~~C++
// add a function
short count()
{
    return data.use_count(); // in StrBlob
    // return wptr.use_count(); in StrBlobPtr
}

int main()
{
    StrBlob str({ "hello", "world" });
    cout << "before: " << str.count() << endl; // 1
    StrBlob str_cp(str);
    cout << "after: " << str.count() << endl;  // 2

    StrBlobPtr p(str);
    cout << "before: " << p.count() << endl; // 2
    StrBlobPtr p_cp(p);
    cout << "after: " << p.count() << endl; // 2 
}
~~~

### 13.4

~~~C++
Point global;
Point foo_bar(Point arg)// 1
{
    Point local = arg, *heap = new Point(global);// 2 3
    *heap = local;
    Point pa[ 4 ] = { local, *heap };// 4 5
    return *heap; // 6
}
~~~

### 13.5

~~~C++
class HasPtr
{
public:
    HasPtr(const string &s = string()) : ps(new string(s)), i(0) {}
    HasPtr(const HasPtr &hp) : ps(new string(*hp.ps)), i(ps.i) {}

private:
    string *ps;
    int i;
};
~~~

### 13.6

1. 拷贝赋值运算符是函数，通常命名为 `operator=` ， 参数与类相同
2. 当赋值时发生
3. 合成拷贝赋值运算符如果不是 `private` 等禁止状态，则会将右侧相应成员赋值给左侧
4. 当该类没有定义自己的拷贝赋值运算符

### 13.7

都会浅拷贝， `use_count` 会发生与  `13.3` 一样的情况

### 13.8

~~~C++
#include <iostream>
#include <string>
#include <vector>
#include <map>
#include <set>
#include <memory>
#include <sstream>
#include <algorithm>
#include <fstream>
#include <ctype.h>
using namespace std;
class HasPtr
{
public:
    HasPtr(const string &s = string()) : ps(new string(s)), i(0) {}
    HasPtr(const HasPtr &hp) : ps(new string(*hp.ps)), i(hp.i) {}
    HasPtr &operator=(const HasPtr &right)
    {
        if (this != &right)
        {
            string *s = new string(*right.ps);
            delete ps;
            ps = s;
            i = right.i;
        }
        return *this;
    }
    void pr()
    {
        cout << *ps << endl;
    }
    void change(string a)
    {
        *ps = a;
    }

private:
    string *ps;
    int i;
};
int main()
{
    HasPtr a("world"), b;
    a.pr(), b.pr();
    b = a;
    a.change("hello");
    a.pr(), b.pr();
    getchar();
    return 0;
}
~~~

### 13.9

1. 析构函数是类名以 `~` 为前缀的成员函数
2. 对某些类可以放进 `private` 里控制类禁止被销毁，一般函数体内就是空的
3. 当类没有定义自己的析构函数的时候

### 13.10

1. `StrBlob` ：`use_count` 递减，如果动态对象已经没有`shared_ptr` 的指向，则销毁
2. `StrBlobPtr` ：直接销毁，指向对象不析构

### 13.11

~~~C++
class HasPtr
{
public:
    HasPtr(const string &s = string()) : ps(new string(s)), i(0) {}
    ~HasPtr() { delete ps; } // add: delete ps;
    HasPtr(const HasPtr &hp) : ps(new string(*hp.ps)), i(hp.i) {}
    HasPtr &operator=(const HasPtr &right)
    {
        if (this != &right)
        {
            string *s = new string(*right.ps);
            delete ps;
            ps = s;
            i = right.i;
        }
        return *this;
    }
    void pr()
    {
        cout << *ps << endl;
    }
    void change(string a)
    {
        *ps = a;
    }

private:
    string *ps;
    int i;
};
~~~

### 13.12

~~~C++
bool fun(const Sales_data *trans, Sales_data accum)
{
    Sales_data item1(*trans), item2(accum);
    return item1.isbn() != item2.isbn();
}
// 3: accum, item1, item2
~~~

### 13.13

 ~~~C++
#include <iostream>
#include <string>
#include <vector>
#include <map>
#include <set>
#include <memory>
#include <sstream>
#include <algorithm>
#include <fstream>
#include <ctype.h>
using namespace std;
struct X
{
    X() { cout << "X()" << endl; }
    X(const X &) { cout << "X(const X&)" << endl; }
    X &operator=(const X &)
    {
        cout << "X& operator=" << endl;
        return *this;
    }
    ~X() { cout << "~X()" << endl; }
};
void f(const X &rx, X x)
{
    vector<X> vec;
    vec.reserve(2);
    vec.push_back(rx);
    vec.push_back(x);
}
int main()
{
    X *ps = new X;
    X a;
    *ps = a;
    f(*ps, *ps);
    delete ps;
    getchar();
    return 0;
}
 ~~~

### 13.14

~~~C++
void f (numbered s) { cout << s.mysn <<endl; }

numbered a, b = a, c = b;
f(a); f(b); f(c);
// Three identical numbers
~~~

### 13.15

拷贝构造函数会生成新的序号，最后会输出三个不同的序号，并且并非是我们想要的`a`, `b`, `c`的编号，因为进入 `f()` 时还会进行一次拷贝构造

### 13.16

会改变，因为 `f()` 传参不用调用拷贝构造函数了，此次输出的序号就是我们想要的`a`, `b`, `c`的编号

### 13.17

~~~C++
#include <iostream>
class numbered
{
public:
    numbered()
    {
        mysn = unique++;
    }
    
    // 13.15 add the function
    numbered(const numbered &temp)
    {
        mysn = unique++;
    }
    
    int mysn;
    static int unique;
};

int numbered::unique = 10;

// 13.16 add const .. &
void f(const numbered &s)
{
    std::cout << s.mysn << std::endl;
}

int main()
{
    numbered a, b = a, c = b;
    f(a);
    f(b);
    f(c);
    getchar();
    return 0;
}
~~~

### 13.18

~~~C++
#include <iostream>
#include <string>
class Employee
{
    std::string name;
    int id;
    static int num;

public:
    Employee();
    Employee(std::string s = "Me") : name(s) { id = num++; }
    void print()
    {
        std::cout << id << " "
                  << name << std::endl;
    }
};
int Employee::num = 10;

int main()
{
    Employee a;
    Employee b;
    a.print();
    b.print();
    getchar();
    return 0;
}
~~~

### 13.19

~~~C++
// no, because there really is no sensible meaning. employee can't copy in real world.

Employee(const Employee&) = delete;
Employee& operator=(const Employee&) = delete; 
~~~

### 13.20

`TextQuery` 和 `QueryResult` 的成员是用智能指针来管理动态内存，因此当我们拷贝、赋值或销毁类对象的时候引用计数会发生改变乃至被销毁

### 13.21

不需要，因为`TextQuery` 和 `QueryResult` 的成员是用智能指针来管理动态内存的

### 13.22 & 13.23

~~~C++
class HasPtr
{
public:
    HasPtr(const string &s = string()) : ps(new string(s)), i(0) {}
    ~HasPtr() { delete ps; }
    HasPtr(const HasPtr &hp) : ps(new string(*hp.ps)), i(hp.i) {}
    HasPtr &operator=(const HasPtr &right)
    {
        // delete "if (this != &right)"
        string *s = new string(*right.ps);
        delete ps;
        ps = s;
        i = right.i;
        return *this;
    }

private:
    string *ps;
    int i;
};
~~~

### 13.24

没有析构函数，合成的析构函数将不会释放内存

没有构造拷贝函数，合成的函数将默认使用指针赋值，两个指针将指向同一个对象

### 13.25

两个函数需要在拷贝的时候新开内存给智能指针，而不是共享对象，不用析构函数是因为智能指针会自动在合成析构函数中被释放，如果 `use_count()` 为 `0` 的话

### 13.26

~~~C++
class StrBlob{
    ...
    // copy constructor
    StrBlob(const StrBlob &sb) : data(make_shared<vector<string>>(*sb.data)) {}
    // copyassignment operators
    StrBlob &operator=(const StrBlob &sb)
    {
        data = make_shared<vector<string>>(*sb.data);
        return *this;
    };
    ...
}
~~~

### 13.27

~~~C++
class HasPtr{
    HasPtr(const string &s = string()) : ps(new string(s)), i(0), use(new size_t(1)){}
    HasPtr(const HasPtr &p) : ps(p.ps), i(p.i), use(p.use){++*use;}
    HasPtr& operator=(const HasPtr& rhs){
        ++*rhs.use;
        if(--*use == 0){
            delete ps;
            delete use;
        }
        ps = rhs.ps;
        use = rhs.use;
        i = rhs.i;
        return *this;
    }
    ~HasPtr(){
        if(--*use == 0){
            delete use;
            delete ps;
        }
    }
private:
    string *ps;
    int i;
    size_t *use;
};
~~~

### 13.28

~~~C++
// (a)
class TreeNode{
    TreeNode() : value(string()), count(0), left(nullptr), right(nullptr){}
    
    TreeNode(const string &s, int c) : value(s), count(c), left(nullptr), right(nullptr){}
    
    ~TreeNode(){
		delete left;
		delete right;
    }
    
    TreeNode(const TreeNode &rhs) ; value(rhs.value), count(rhs.count){
        if(rhs.left)
            left = new TreeNode(*rhs.left);
        if(rhs.right)
            right = new TreeNode(*rhs.right);
    }
    
    TreeNode &operator=(const TreeNode &rhs){
        value = rhs.value;
        count = rhs.count;
        TreeNode *temp = nullptr;
        
        if(rhs.left)
            temp = new TreeNode(*rhs.left);
        delete left;
        left = temp;
        
        temp = nullptr;
        
        if(rhs.right)
            temp = new TreeNode(*rhs.right);
        delete right;
        right = temp;
        
        delete temp;
        return *this;
    }
    
private:
    	string value;
    	int	count;
    	TreeNode *left;
    	TreeNode *right;
};

// (b)

class BinStrTree{
    BinStrTree(const TreeNode &t = TreeNode()) : root(new TreeNode(t)), use(new size_t(1)){}
    
    BinStrTree(const BinStrTree &rhs) : root(new TreeNode(*rhs.root)), use(rhs.use){++*use;}
    
    ~BinStrTree(){
        if(--*use == 0){
            delete root;
            delete use;
        }
    }
    
    BinStrTree& operator=(const BinStrTree& rhs){
        ++*rhs.use;
        if(--*use == 0){
            delete use;
            delete root;
        }
        root = rhs.root;
        use = rhs.use;
        
        return *this;
    }
    
private:
    TreeNode *root;
    size_t *use;
};
~~~

### 13.29

`swap(lhs.ps, rhs.ps);` : `swap(string*, string*)`

`swap(lhs.i, rhs.i);` : `swap(int, int)`

### 13.30

~~~C++
class HasPtr
{
    HasPtr(const string &s = string()) : ps(new string(s)), i(0), use(new size_t(1)) {}
    HasPtr(const HasPtr &p) : ps(p.ps), i(p.i), use(p.use) { ++*use; }
    HasPtr &operator=(const HasPtr &rhs)
    {
        ++*rhs.use;
        if (--*use == 0)
        {
            delete ps;
            delete use;
        }
        ps = rhs.ps;
        use = rhs.use;
        i = rhs.i;
        return *this;
    }
    ~HasPtr()
    {
        if (--*use == 0)
        {
            delete use;
            delete ps;
        }
    }
    
    friend void swap(HasPtr &, HasPtr &);

private:
    string *ps;
    int i;
    size_t *use;
};

inline void swap(HasPtr &lhs, HasPtr &rhs)
{
    swap(lhs.ps, rhs.ps);
    swap(lhs.i, rhs.i);
    cout << "call swap(HasPtr& lhs, HasPtr& rhs)" << endl;
}
~~~

### 13.31

~~~C++
#include <iostream>
#include <vector>
#include <string>
#include <algorithm>
using namespace std;
class HasPtr
{
public:
    HasPtr(const string &s = string()) : ps(new string(s)), i(0), use(new size_t(1)) {}
    HasPtr(const HasPtr &p) : ps(p.ps), i(p.i), use(p.use) { ++*use; }
    HasPtr &operator=(HasPtr rhs)
    {
        swap(*this, rhs);
        return *this;
    }
    ~HasPtr()
    {
        if (--*use == 0)
        {
            delete use;
            delete ps;
        }
    }
    void show() const
    {
        cout << *ps << endl;
    }
    friend bool operator<(const HasPtr &lhs, const HasPtr &rhs);
    friend void swap(HasPtr &, HasPtr &);

private:
    string *ps;
    int i;
    size_t *use;
};

inline void swap(HasPtr &lhs, HasPtr &rhs)
{
    swap(lhs.ps, rhs.ps);
    swap(lhs.i, rhs.i);
    cout << "call swap(HasPtr& lhs, HasPtr& rhs)" << endl;
}

bool operator<(const HasPtr &lhs, const HasPtr &rhs)
{
    return *lhs.ps < *rhs.ps;
}
int main()
{
    HasPtr s{"s"}, a{"a"}, c{"c"};
    vector<HasPtr> vec{s, a, c};
    sort(vec.begin(), vec.end());
    for (auto const &elem : vec)
        elem.show();
    return 0;
}
~~~

### 13.32

不会， `swap` 函数的益处本质在于交换指针而避免额外的内存开销，类指针的 `HasPtr` 版本就是指针交换

### 13.33



