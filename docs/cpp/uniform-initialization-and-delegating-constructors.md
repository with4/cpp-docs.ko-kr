---
title: "균일 초기화 및 생성자 위임 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: aa4daa64-eaec-4a3c-ade4-d9325e31e9d4
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# 균일 초기화 및 생성자 위임
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

최신 C\+\+에서는 등호 기호 없이 어떤 형식이던지 *중괄호 초기화* 사용할 수 있습니다.  또한, 비슷한 작업을 수행하는 생성자가 여러 개 있을 때 코드를 단순화 하기위해 위임된 생성자를 사용할 수 있습니다.  
  
## 중괄호 초기화  
 중괄호 초기화는 클래스, 구조체 또는 공용 구조체에 사용할 수 있습니다.  형식에 암시적으로 또는 명시적으로 선언된 기본 생성자가 있는 경우, 기본 중괄호 초기화\(빈 중괄호와 함께\)를 사용할 수 있습니다.  예를 들어, 다음 클래스는 기본 및 기본이 아닌 중괄호 초기화를 사용하여 초기화할 수 있습니다.  
  
```cpp  
#include <string>  
using namespace std;  
  
class class_a {  
public:  
    class_a() {}  
    class_a(string str) : m_string{ str } {}  
    class_a(string str, double dbl) : m_string{ str }, m_double{ dbl } {}  
double m_double;  
string m_string;  
};  
  
int main()  
{  
    class_a c1{};  
    class_a c1_1;  
  
    class_a c2{ "ww" };  
    class_a c2_1("xx");  
  
    // order of parameters is the same as the constructor  
    class_a c3{ "yy", 4.4 };  
    class_a c3_1("zz", 5.5);  
}  
  
```  
  
 클래스에 기본이 아닌 생성자를 가질 경우, 중괄호 이니셜라이저에 클래스 멤버가 나타나는 순서는 멤버는 선언된 순서가 아니라 \( `class_a`  이전 예제에서와 마찬가지로 \) 생성자에서 해당 매개 변수가 나타나는 순서입니다.  그렇지 않고 해당 형식이 선언 된 생성자를 가지지 않을 경우, 중괄호 이니셜라이저에서 멤버가 나타나는 순서는 선언되어 있는 순서와 동일합니다; 이 경우, 대부분의 공용 멤버를 초기화할 수 있지만 모든 멤버를 건너뛸 수는 없습니다.  다음 예제에서는 선언 된 생성자가 없을 때 중괄호 초기화에서 사용되는 순서를 보여줍니다.  
  
```cpp  
class class_d {  
public:  
    float m_float;  
    string m_string;  
    wchar_t m_char;  
};  
  
int main()  
{  
    class_d d1{};  
    class_d d1{ 4.5 };  
    class_d d2{ 4.5, "string" };  
    class_d d3{ 4.5, "string", 'c' };  
  
    class_d d4{ "string", 'c' }; // compiler error  
    class_d d5("string", 'c', 2.0 }; // compiler error  
}   
```  
  
 기본 생성자가 명시적으로 선언 되었지만 삭제 된 것으로 표시되었을 경우, 중괄호 기본 초기화를 사용할 수 없습니다.  
  
```cpp  
class class_f {  
public:  
    class_f() = delete;  
    class_f(string x): m_string { x } {}  
    string m_string;  
};  
int main()  
{  
    class_f cf{ "hello" };  
    class_f cf1{}; // compiler error C2280: attempting to reference a deleted function  
}  
```  
  
 일반적으로 초기화할 수 있는 곳 어디에서나 중괄호 초기화를 사용할 수 있습니다. \-예를 들어, 함수 매개 변수, 반환 값 또는  `new`  키워드와 함께 :  
  
```cpp  
class_d* cf = new class_d{4.5};  
kr->add_d({ 4.5 });  
return { 4.5 };  
  
```  
  
## initializer\_list 생성자  
 [initializer\_list Class](../standard-library/initializer-list-class.md) 는 생성자와 다른 컨텍스트에서 사용할 수 있는 지정된 형식의 개체 목록을 나타냅니다.  Initializer\_list는 중괄호 초기화를 사용하여 생성자 리스트를 구성할 수 있습니다.  
  
```cpp  
initializer_list<int> int_list{5, 6, 7};  
```  
  
> [!IMPORTANT]
>  이 클래스를 사용하여 [\<initializer\_list\>](../standard-library/initializer-list.md) 헤더를 반드시 포함해야됩니다.  
  
 `initializer_list`  를 복사할 수 있습니다.  이 경우, 새 목록의 구성원은 원래 그룹의 구성원에 대한 참조입니다:  
  
```cpp  
initializer_list<int> ilist1{ 5, 6, 7 };  
initializer_list<int> ilist2( ilist1 );  
if (ilist1.begin() == ilist2.begin())  
    cout << "yes" << endl; // expect "yes"  
  
```  
  
 표준 라이브러리 컨테이너 클래스와  `string` ,  `wstring` , 및  `regex` 는  `initializer_list`  생성자를 가집니다.  다음 예제에서는 이 생성자를 사용하여 초기화 중괄호를 수행하는 방법을 보여줍니다.  
  
```cpp  
vector<int> v1{ 9, 10, 11 };   
map<int, string> m1{ {1, "a"}, {2, "b"} };  
string s{ 'a', 'b', 'c' };   
regex rgx{'x', 'y', 'z'};   
```  
  
## 위임 생성자  
 대부분의 클래스는 비슷한 작업을 수행하는 여러 생성자를 가집니다\-예를 들어, 매개 변수 유효성 검사.  
  
```cpp  
class class_c {  
public:  
    int max;  
    int min;  
    int middle;  
  
    class_c() {}  
    class_c(int my_max) {   
        max = my_max > 0 ? my_max : 10;   
    }  
    class_c(int my_max, int my_min) {   
        max = my_max > 0 ? my_max : 10;  
        min = my_min > 0 && my_min < max ? my_min : 1;  
    }  
    class_c(int my_max, int my_min, int my_middle) {  
        max = my_max > 0 ? my_max : 10;  
        min = my_min > 0 && my_min < max ? my_min : 1;  
        middle = my_middle < max && my_middle > min ? my_middle : 5;  
    }  
};  
```  
  
 모든 수행 하는 함수를 추가하여 반복 되는 코드를 줄일 수 있지만,  `class_c` 의 코드는  생성자가 작업 일부를 위임할 수 있는지에 대한 이해 및 유지가 더 쉽게 이루어집니다.  위임 생성자를 추가하려면  `constructor (. . .) : constructor (. . .)`  구문을 사용합니다:  
  
```cpp  
class class_c {  
public:  
    int max;  
    int min;  
    int middle;  
  
    class_c(int my_max) {   
        max = my_max > 0 ? my_max : 10;   
    }  
    class_c(int my_max, int my_min) : class_c(my_max) {   
        min = my_min > 0 && my_min < max ? my_min : 1;  
    }  
    class_c(int my_max, int my_min, int my_middle) : class_c (my_max, my_min){  
        middle = my_middle < max && my_middle > min ? my_middle : 5;  
}  
};  
int main() {  
  
    class_c c1{ 1, 3, 2 };  
}  
  
```  
  
 위 예제를 단계별로 수행했다면,   `class_c(int, int, int)`  생성자가 `class_c(int)`을 다시 호출하는  `class_c(int, int)` 생성자를 호출하는 것을 주목합니다.  각 생성자는 다른 생성자에서 수행되지 않는 작업만을 수행합니다.  
  
 호출하는 첫번째 생성자는 해당 지점에서 해당 멤버 모두가 초기화되도록 개체를 초기화합니다.  다음과 같이 다른 생성자에 위임하는 생성자의 멤버를 초기화할 수 없습니다.  
  
```cpp  
class class_a {  
public:  
    class_a() {}  
    // member initialization here, no delegate  
    class_a(string str) : m_string{ str } {}  
  
    //can’t do member initialization here  
    // error C3511: a call to a delegating constructor shall be the only member-initializer  
    class_a(string str, double dbl) : class_a(str) , m_double{ dbl } {}  
  
    // only member assignment  
    class_a(string str, double dbl) : class_a(str) { m_double = dbl; }  
    double m_double{ 1.0 };  
    string m_string;  
};  
  
```  
  
 다음 예제에서는 비정적 데이터 멤버 이니셜라이저의 사용을 보여줍니다.  생성자는 주어진 데이터 멤버 또한 초기화할 경우, 멤버 이니셜라이저 재정의됩니다.  
  
```cpp  
class class_a {  
public:  
    class_a() {}  
    class_a(string str) : m_string{ str } {}  
    class_a(string str, double dbl) : class_a(str) { m_double = dbl; }  
    double m_double{ 1.0 };  
    string m_string{ m_double < 10.0 ? "alpha" : "beta" };  
};  
  
int main() {  
    class_a a{ "hello", 2.0 };  //expect a.m_double == 2.0, a.m_string == "hello"  
    int y = 4;  
}  
```  
  
 위임 생성자 구문이 생성자 재귀를 실수로 작성 해도\-Constructor1가 Constructor1를 호출하는 Constructor2을 호출\- 스택 오버플로 때까지 오류 없이 throw 됩니다.  주기를 방지하기 위한 책임이 있습니다.  
  
```cpp  
class class_f{  
public:  
    int max;  
    int min;  
  
    // don't do this  
    class_f() : class_f(6, 3){ }  
    class_f(int my_max, int my_min) : class_f() { }  
};  
```