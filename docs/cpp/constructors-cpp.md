---
title: "생성자 (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "생성자[C++]"
  - "인스턴스 생성자"
  - "개체[C++], 만들기"
ms.assetid: 3e9f7211-313a-4a92-9584-337452e061a9
caps.latest.revision: 17
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 생성자 (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

생성자는 해당 클래스의 인스턴스를 초기화하는 일종의 멤버 함수입니다.  생성자는 클래스와 같은 이름을 사용하며 반환 값이 없습니다.  생성자는 원하는 수의 매개 변수를 사용할 수 있으며 클래스는 원하는 수의 오버로드된 생성자를 사용할 수 있습니다.  생성자에는 접근성, public, protected 또는 private이 있을 수 있습니다.  생성자를 정의하지 않는 경우 컴파일러는 매개 변수를 사용하지 않는 기본 생성자를 생성합니다. 기본 생성자를 삭제된 것으로 선언하여 이 동작을 재정의할 수 있습니다.  
  
## 항목 내용  
  
-   [생성 순서](#order_of_construction)  
  
-   [멤버 목록](../cpp/constructors-cpp.md#member_lists)  
  
-   [명시적 생성자](../cpp/constructors-cpp.md#explicit_constructors)  
  
-   [기본 생성자](../cpp/constructors-cpp.md#default_constructors)  
  
-   [복사 및 이동 생성자](../cpp/constructors-cpp.md#copy_and_move_constructors)  
  
-   [명시적 기본값으로 설정된 생성자 및 삭제된 생성자](../cpp/constructors-cpp.md#explicitly_defaulted_and_deleted_constructors)  
  
-   [파생 클래스의 생성자](../cpp/constructors-cpp.md#constructors_in_derived_classes)  
  
-   [다중 상속을 포함하는 클래스에 대한 생성자](../cpp/constructors-cpp.md#constructors_for_classes_that_have_multiple_inheritance)  
  
-   [생성자의 가상 함수](../cpp/constructors-cpp.md#virtual_functions_in_constructors)  
  
-   [생성자 및 복합 클래스](../cpp/constructors-cpp.md#constructors_in_composite_classes)  
  
-   [위임 생성자](../cpp/constructors-cpp.md#delegating_constructors)  
  
-   [상속 생성자(C++11)](../cpp/constructors-cpp.md#inheriting_constructors)  
  
-   [생성자를 선언하기 위한 규칙](../cpp/constructors-cpp.md#rules_for_declaring_constructors)  
  
-   기본 및 복사 생성자  
  
-   [생성자를 명시적으로 호출](../cpp/constructors-cpp.md#explicitly_invoking_constructors)  
  
##  <a name="order_of_construction"></a> 생성 순서  
 생성자는 다음과 같은 순서로 작업을 수행합니다.  
  
1.  생성자는 선언 순서대로 기본 클래스 및 멤버 생성자를 호출합니다.  
  
2.  클래스가 가상 기본 클래스에서 파생된 경우 해당 클래스는 개체의 가상 기본 포인터를 초기화합니다.  
  
3.  클래스가 가상 함수를 포함하거나 상속하는 경우 해당 클래스는 개체의 가상 함수 포인터를 초기화합니다.  가상 함수 포인터는 클래스의 가상 함수 테이블을 가리켜서 가상 함수 호출의 올바른 바인딩이 코딩되도록 합니다.  
  
4.  이러한 포인터는 함수 본문의 모든 코드를 실행합니다.  
  
 다음 예제에서는 파생 클래스의 생성자에서 기본 클래스 및 멤버 생성자가 호출되는 순서를 보여 줍니다.  먼저 기본 생성자를 호출하고, 기본 클래스 멤버를 클래스 선언에 표시되는 순서대로 초기화한 다음 파생된 생성자를 호출합니다.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
class Contained1 {  
public:  
    Contained1() {  
        cout << "Contained1 constructor." << endl;  
    }  
};  
  
class Contained2 {  
public:  
    Contained2() {  
        cout << "Contained2 constructor." << endl;  
    }  
};  
  
class Contained3 {  
public:  
    Contained3() {  
        cout << "Contained3 constructor." << endl;  
    }  
};  
  
class BaseContainer {  
public:  
    BaseContainer() {  
        cout << "BaseContainer constructor." << endl;  
    }  
private:  
    Contained1 c1;  
    Contained2 c2;  
};  
  
class DerivedContainer : public BaseContainer {  
public:  
    DerivedContainer() : BaseContainer() {  
        cout << "DerivedContainer constructor." << endl;  
    }  
private:  
    Contained3 c3;  
};  
  
int main() {  
    DerivedContainer dc;  
    int x = 3;  
}  
  
```  
  
 출력은 다음과 같습니다.  
  
```  
Contained1 constructor.  
Contained2 constructor.  
BaseContainer constructor.  
Contained3 constructor.  
DerivedContainer constructor.  
```  
  
 생성자가 예외를 throw하는 경우 소멸 순서는 생성의 역순입니다.  
  
1.  생성자 함수 본문의 코드가 해제됩니다.  
  
2.  기본 클래스 및 멤버 개체가 선언의 역순으로 소멸됩니다.  
  
3.  생성자가 비대리자인 경우 제대로 생성된 기본 클래스 개체 및 멤버가 모두 소멸됩니다.  하지만 개체가 완전히 생성되지 않으므로 소멸자는 실행되지 않습니다.  
  
##  <a name="member_lists"></a> 멤버 목록  
 멤버 이니셜라이저 목록을 사용하여 생성자 인수에서 클래스 멤버를 초기화합니다.  이 메서드는 생성자 본문 내에서 할당 연산자를 사용하는 것보다 더 효율적인 *직접 초기화*를 사용합니다.  
  
```cpp  
class Box {  
public:  
    Box(int width, int length, int height)   
        : m_width(width), m_length(length), m_height(height) // member init list  
    {}  
    int Volume() {return m_width * m_length * m_height; }  
private:  
    int m_width;  
    int m_length;  
    int m_height;  
  
};  
  
```  
  
 Box 개체 만들기:  
  
```  
Box b(42, 21, 12);  
cout << "The volume is " << b.Volume();  
```  
  
##  <a name="explicit_constructors"></a> 명시적 생성자  
 클래스에 단일 매개 변수를 사용하는 생성자가 있거나 하나를 제외한 모든 매개 변수에서 기본값을 사용하는 경우 이 매개 변수 형식은 클래스 형식으로 암시적으로 변환할 수 있습니다.  예를 들어 `Box` 클래스에 다음과 같은 생성자가 있는 경우입니다.  
  
```  
Box(int size): m_width(size), m_length(size), m_height(size){}  
```  
  
 다음과 같이 Box를 초기화할 수 있습니다.  
  
```  
Box b = 42;  
```  
  
 또는 Box를 사용하는 함수에 int를 전달합니다.  
  
```  
class ShippingOrder  
{  
public:  
    ShippingOrder(Box b, double postage) : m_box(b), m_postage(postage){}  
  
private:  
    Box m_box;  
    double m_postage;  
}  
//elsewhere...  
    ShippingOrder so(42, 10.8);  
  
```  
  
 경우에 따라 이러한 변환은 유용할 수 있지만 코드에서 미세하지만 심각한 오류를 발생시키는 경우가 더 자주 있습니다.  일반적으로 이러한 종류의 암시적 형식 변환을 방지하려면 생성자\(및 사용자 정의 연산자\)에서 `explicit` 키워드를 사용해야 합니다.  
  
```  
  
explicit Box(int size): m_width(size), m_length(size), m_height(size){}  
```  
  
 생성자가 명시적인 경우 `ShippingOrder so(42, 10.8);` 줄에서 컴파일 오류가 발생합니다.  자세한 내용은 [변환](../cpp/user-defined-type-conversions-cpp.md)을 참조하세요.  
  
##  <a name="default_constructors"></a> 기본 생성자  
 *기본 생성자*는 매개 변수가 없으며, 약간 다른 규칙을 따릅니다.  
  
 기본 생성자는 *특수 멤버 함수* 중 하나입니다. 클래스에 선언된 생성자가 없는 경우 컴파일러에서 기본 생성자를 제공합니다.  
  
```cpp  
class Box {  
    Box(int width, int length, int height)   
        : m_width(width), m_length(length), m_height(height){}  
};  
  
int main(){  
  
    Box box1{}; // call compiler-generated default ctor  
    Box box2;   // call compiler-generated default ctor  
}  
```  
  
 기본 생성자를 호출하고 괄호를 사용하면 경고가 표시됩니다.  
  
```cpp  
class myclass{};  
int main(){  
myclass mc();     // warning C4930: prototyped function not called (was a variable definition intended?)  
}  
```  
  
 이는 가장 까다로운 구문 분석 문제의 한 예입니다.  예제 식을 함수 선언 또는 기본 생성자 호출로 해석할 수 있고 C\+\+ 파서에서는 선언을 다른 항목보다 우선하므로 식이 함수 선언으로 처리됩니다.  자세한 내용은 [가장 까다로운 구문 분석](http://en.wikipedia.org/wiki/Most_vexing_parse)을 참조하세요.  
  
 기본값이 아닌 생성자가 선언된 경우 컴파일러는 기본 생성자를 제공하지 않습니다.  
  
```cpp  
class Box {  
    Box(int width, int length, int height)   
        : m_width(width), m_length(length), m_height(height){}  
};  
private:  
    int m_width;  
    int m_length;  
    int m_height;  
  
};  
  
int main(){  
  
    Box box1(1, 2, 3);  
    Box box2{ 2, 3, 4 };  
    Box box4;     // compiler error C2512: no appropriate default constructor available  
}  
  
```  
  
 클래스에 기본 생성자가 없는 경우 대괄호 구문만 사용하여 해당 클래스의 개체 배열을 생성할 수 없습니다.  예를 들어 이전 코드 블록에서 다음과 같이 상자 배열을 선언할 수 없습니다.  
  
```cpp  
Box boxes[3];    // compiler error C2512: no appropriate default constructor available  
  
```  
  
 하지만 다음과 같이 이니셜라이저 목록 집합을 사용하여 상자 배열을 초기화할 수 있습니다.  
  
```cpp  
Box boxes[3]{ { 1, 2, 3 }, { 4, 5, 6 }, { 7, 8, 9 } };  
```  
  
##  <a name="copy_and_move_constructors"></a> 복사 및 이동 생성자  
 *복사 생성자*는 동일한 형식의 개체에 대한 참조를 입력으로 사용하고 복사본을 만드는 특수 멤버 함수입니다.  자세한 내용은 [복사 생성자 및 복사 할당 연산자\(C\+\+\)](../cpp/copy-constructors-and-copy-assignment-operators-cpp.md)를 참조하세요.  이동 생성자 또한 특수 멤버 함수이며, 이 생성자는 원래 데이터를 복사하지 않고 기존 개체의 소유권을 새 변수로 이동합니다.  자세한 내용은 [이동 생성자 및 이동 할당 연산자\(C\+\+\)](http://msdn.microsoft.com/ko-kr/1442de5f-37a5-42a1-83a6-ec9cfe0414db) 및 [이동 생성자 및 이동 할당 연산자\(C\+\+\)](../cpp/move-constructors-and-move-assignment-operators-cpp.md)을 참조하세요.  
  
##  <a name="explicitly_defaulted_and_deleted_constructors"></a> 명시적 기본값으로 설정된 생성자 및 삭제된 생성자  
 복사 생성자, 기본 생성자, 이동 생성자, 복사 할당 연산자, 이동 할당 연산자 및 소멸자를 명시적으로 기본값으로 설정할 수 있습니다.  모든 특수 함수를 명시적으로 삭제할 수 있습니다.  자세한 내용은 [명시적으로 기본 설정 및 삭제된 함수](../cpp/explicitly-defaulted-and-deleted-functions.md)를 참조하세요.  
  
##  <a name="constructors_in_derived_classes"></a> 파생 클래스의 생성자  
 파생 클래스 생성자는 항상 기본 클래스 생성자를 호출하므로, 완전히 생성된 기본 클래스를 통해서만 다른 작업을 수행할 수 있습니다.  기본 클래스 생성자는 파생 순서대로 호출됩니다. 예를 들어 ClassA는 ClassB에서 파생되고, ClassB는 ClassC에서 파생될 경우 ClassC 생성자, ClassB 생성자, ClassA 생성자의 순으로 호출됩니다.  
  
 기본 클래스에 기본 생성자가 없는 경우 파생 클래스 생성자에 기본 클래스 생성자 매개 변수를 제공해야 합니다.  
  
```cpp  
class Box {  
public:  
    Box(int width, int length, int height){  
       m_width = width;  
       m_length = length;  
       m_height = height;  
    }  
  
private:  
    int m_width;  
    int m_length;  
    int m_height;  
};  
  
class StorageBox : public Box {  
public:  
    StorageBox(int width, int length, int height, const string label&) : Box(width, length, height){  
        m_label = label;  
    }  
private:  
    string m_label;  
};  
  
int main(){  
  
    const string aLabel = "aLabel";  
    StorageBox sb(1, 2, 3, aLabel);  
}   
```  
  
### 다중 상속을 포함하는 클래스에 대한 생성자  
 클래스가 여러 기본 클래스에서 파생되는 경우 기본 클래스 생성자는 파생 클래스 선언에 나열된 순서대로 호출됩니다.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
class BaseClass1 {  
public:  
    BaseClass1() {  
        cout << "BaseClass1 constructor." << endl;  
    }  
};  
class BaseClass2 {  
public:  
    BaseClass2() {  
        cout << "BaseClass2 constructor." << endl;  
    }  
};  
class BaseClass3{  
public:  
    BaseClass3() {  
        cout << "BaseClass3 constructor." << endl;  
    }  
};  
class DerivedClass : public BaseClass1, public BaseClass2, public BaseClass3  {  
public:  
    DerivedClass() {  
        cout << "DerivedClass constructor." << endl;  
    }  
};  
  
int main() {  
    DerivedClass dc;  
}  
  
```  
  
 다음과 같이 출력됩니다.  
  
```  
BaseClass1 constructor.  
BaseClass2 constructor.  
BaseClass3 constructor.  
DerivedClass constructor.  
```  
  
##  <a name="virtual_functions_in_constructors"></a> 생성자의 가상 함수  
 생성자에서 가상 함수를 호출할 경우 주의하시기 바랍니다.  기본 클래스 생성자가 파생 클래스 생성자보다 항상 먼저 호출되므로, 기본 생성자에서 호출되는 함수는 파생 클래스 버전이 아닌 기본 클래스 버전입니다.  다음 예제에서 `DerivedClass`를 생성하면 `BaseClass` 생성자에 의해 `print_it()`의 `DerivedClass` 구현이 실행되기 이전에 `DerivedClass`의 `print_it()` 구현이 실행됩니다.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
class BaseClass{  
public:  
    BaseClass(){  
        print_it();  
    }  
    virtual void print_it() {  
        cout << "BaseClass print_it" << endl;  
    }  
};  
  
class DerivedClass : public BaseClass {  
public:  
    DerivedClass() {  
        print_it();  
    }  
    virtual void print_it(){  
        cout << "Derived Class print_it" << endl;  
    }  
};  
  
int main() {  
  
    DerivedClass dc;  
}  
```  
  
 출력은 다음과 같습니다.  
  
```  
BaseClass print_it  
Derived Class print_it  
```  
  
##  <a name="constructors_in_composite_classes"></a> 생성자 및 복합 클래스  
 클래스 형식 멤버를 포함하는 클래스를 *복합 클래스*라고 합니다.  복합 클래스의 클래스 형식 멤버를 만들 때 생성자가 클래스의 자체 생성자보다 먼저 호출됩니다.  포함된 클래스에 기본 생성자가 없는 경우 복합 클래스의 생성자에서 초기화 목록을 사용해야 합니다.  이전 `StorageBox` 예제에서 `m_label` 멤버 변수의 형식을 새 `Label` 클래스로 변경할 경우 기본 클래스 생성자를 호출하고 `m_label` 생성자에서 `StorageBox` 변수를 초기화해야 합니다.  
  
```cpp  
class Label {  
public:  
    Label(const string& name, const string& address) { m_name = name; m_address = address; }  
    string m_name;  
    string m_address;  
};  
  
class StorageBox : public Box {  
public:  
    StorageBox(int width, int length, int height, Label label)   
        : Box(width, length, height), m_label(label){}  
private:  
    Label m_label;  
};  
  
int main(){  
// passing a named Label  
    Label label1{ "some_name", "some_address" };  
    StorageBox sb1(1, 2, 3, label1);  
  
    // passing a temporary label  
    StorageBox sb2(3, 4, 5, Label{ "another name", "another address" });  
  
    // passing a temporary label as an initializer list  
    StorageBox sb3(1, 2, 3, {"myname", "myaddress"});  
}  
```  
  
##  <a name="delegating_constructors"></a> 위임 생성자  
 *위임 생성자*는 동일한 클래스의 다른 생성자를 호출하여 초기화 작업의 일부를 수행합니다.  다음 예제에서는 파생 클래스에 세 개의 생성자가 있는데 두 번째 생성자는 첫 번째 생성자에 위임되고, 세 번째 생성자는 두 번째 생성자에 위임됩니다.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
class ConstructorDestructor {  
public:  
    ConstructorDestructor() {  
        cout << "ConstructorDestructor default constructor." << endl;  
    }  
    ConstructorDestructor(int int1) {  
        cout << "ConstructorDestructor constructor with 1 int." << endl;  
    }  
    ConstructorDestructor(int int1, int int2) : ConstructorDestructor(int1) {  
        cout << "ConstructorDestructor constructor with 2 ints." << endl;  
  
        throw exception();  
    }  
    ConstructorDestructor(int int1, int int2, int int3) : ConstructorDestructor(int1, int2) {  
        cout << "ConstructorDestructor constructor with 3 ints." << endl;  
    }  
    ~ConstructorDestructor() {  
        cout << "ConstructorDestructor destructor." << endl;  
    }  
};  
  
int main() {  
    ConstructorDestructor dc(1, 2, 3);  
}  
  
```  
  
 출력은 다음과 같습니다.  
  
```  
ConstructorDestructor constructor with 1 int.  
ConstructorDestructor constructor with 2 ints.  
ConstructorDestructor constructor with 3 ints.  
```  
  
 생성자에 의해 만들어지는 개체는 생성자가 완료되는 즉시 완전하게 초기화됩니다.  `DerivedContainer(int int1)`는 성공하지만 `DerivedContainer(int int1, int int2)`는 실패하고 소멸자가 호출됩니다.  
  
```cpp  
class ConstructorDestructor {  
public:  
    ConstructorDestructor() {  
        cout << "ConstructorDestructor default constructor." << endl;  
    }  
    ConstructorDestructor(int int1) {  
        cout << "ConstructorDestructor constructor with 1 int." << endl;  
    }  
    ConstructorDestructor(int int1, int int2) : ConstructorDestructor(int1) {  
        cout << "ConstructorDestructor constructor with 2 ints." << endl;  
        throw exception();  
    }  
    ConstructorDestructor(int int1, int int2, int int3) : ConstructorDestructor(int1, int2) {  
        cout << "ConstructorDestructor constructor with 3 ints." << endl;  
    }  
  
    ~ConstructorDestructor() {  
        cout << "ConstructorDestructor destructor." << endl;  
    }  
};  
  
int main() {  
  
    try {  
        ConstructorDestructor cd{ 1, 2, 3 };  
    }  
    catch (const exception& ex){  
    }  
}  
  
```  
  
 출력:  
  
```  
ConstructorDestructor constructor with 1 int.  
ConstructorDestructor constructor with 2 ints.  
ConstructorDestructor destructor.  
```  
  
 자세한 내용은 [균일 초기화 및 생성자 위임](../cpp/uniform-initialization-and-delegating-constructors.md)를 참조하세요.  
  
##  <a name="inheriting_constructors"></a> 상속 생성자\(C\+\+11\)  
 파생 클래스는 다음 예제와 같이 using 선언을 사용하여 직접 기본 클래스에서 생성자를 상속할 수 있습니다.  
  
```  
#include <iostream>  
using namespace std;  
  
class Base  
{  
public:      
    Base() { cout << "Base()" << endl; }  
    Base(const Base& other) { cout << "Base(Base&)" << endl; }  
    explicit Base(int i) : num(i) { cout << "Base(int)" << endl; }  
    explicit Base(char c) : letter(c) { cout << "Base(char)" << endl; }  
  
private:  
    int num;  
    char letter;  
};  
  
class Derived : Base  
{  
public:  
    // Inherit all constructors from Base  
    using Base::Base;  
  
private:  
    // Can't initialize newMember from Base constructors.  
    int newMember{ 0 };  
};  
  
int main(int argc, char argv[])  
{  
    cout << "Derived d1(5) calls: ";   
    Derived d1(5);  
    cout << "Derived d1('c') calls: ";  
    Derived d2('c');  
    cout << "Derived d3 = d2 calls: " ;  
    Derived d3 = d2;  
    cout << "Derived d4 calls: ";  
    Derived d4;   
  
    // Keep console open in debug mode:  
    cout << endl << "Press Enter to exit.";  
    char in[1];  
    cin.getline(in, 1);  
    return 0;  
}  
  
/* Output:  
Derived d1(5) calls: Base(int)  
Derived d1('c') calls: Base(char)  
Derived d3 = d2 calls: Base(Base&)  
Derived d4 calls: Base()  
  
Press Enter to exit.  
  
```  
  
 using 문은 파생 클래스의 생성자와 동일한 서명을 사용하는 생성자를 제외하고 모든 생성자를 기본 클래스에서 범위로 가져옵니다.  일반적으로 파생 클래스에서 새 데이터 멤버나 생성자를 선언하지 않는 경우 상속 생성자를 사용하는 것이 가장 좋습니다.  
  
 클래스 템플릿은 해당 형식이 기본 클래스를 지정하는 경우 형식 인수에서 모든 생성자를 상속할 수 있습니다.  
  
```  
template< typename T >  
class Derived : T {  
    using T::T;   // declare the constructors from T  
    // ...  
};  
  
```  
  
 파생 클래스는 다중 기본 클래스에 동일한 서명을 사용하는 생성자가 있는 경우 해당 다중 기본 클래스에서 상속할 수 없습니다.  
  
##  <a name="rules_for_declaring_constructors"></a> 생성자를 선언하기 위한 규칙  
 생성자의 이름은 해당 클래스의 이름과 같습니다.  오버로드된 함수의 규칙에 따라 임의의 수의 생성자를 선언할 수 있습니다.  자세한 내용은 [오버로드](../misc/overloading-cpp.md)를 참조하세요.  
  
 `argument-declaration-list`가 비어 있을 수 있습니다.  
  
 C\+\+에서는 다음 표에 설명되어 있는 두 가지 특별한 종류의 생성자인 기본 및 복사 생성자를 정의합니다.  
  
### 기본 및 복사 생성자  
  
|생성 종류|인수|용도|  
|-----------|--------|--------|  
|기본 생성자|인수 없이 호출될 수 있습니다.|해당 클래스 형식의 기본 개체를 생성합니다.|  
|복사 생성자|동일한 클래스 형식에 대한 참조의 단일 인수를 수락할 수 있습니다.|클래스 형식의 개체를 복사합니다.|  
  
 기본 생성자는 인수 없이 호출할 수 있습니다.  하지만 모든 인수에 기본값이 제공된 경우 인수 목록을 사용하여 기본 생성자를 선언할 수 있습니다.  마찬가지로 복사 생성자는 동일 클래스 형식에 대한 참조의 단일 인수를 수락해야 합니다.  모든 후속 인수에 기본값이 있는 경우 인수를 추가로 제공할 수 있습니다.  
  
 생성자를 제공하지 않는 경우 컴파일러는 기본 생성자를 생성하려고 합니다.  복사 생성자를 제공하지 않는 경우 컴파일러는 기본 생성자를 생성하려고 합니다.  이 컴파일러에서 생성되는 생성자는 공용 멤버 함수로 간주됩니다.  개체인데 참조가 아닌 첫 번째 인수를 사용하여 복사 생성자를 지정하는 경우 오류가 생성됩니다.  
  
 컴파일러에서 생성되는 기본 생성자는 개체를 설정하고\(앞에서 설명한 vftables 및 vbtables 초기화\) 기본 클래스와 멤버에 대한 기본 생성자를 호출하지만 다른 어떠한 작업도 수행하지 않습니다.  기본 클래스 및 멤버 생성자는 존재하고 액세스할 수 있으며 명확한 경우에만 호출됩니다.  
  
 컴파일러에서 생성되는 복사 생성자는 새 개체를 설정하고 복사할 개체의 콘텐츠에 대해 멤버 방식으로 복사를 수행합니다.  기본 클래스 또는 멤버 생성자가 있으면 호출되고, 그렇지 않으면 비트 복사가 수행됩니다.  
  
 클래스 `type`의 모든 기본 및 멤버 클래스에 **const** 인수를 수락하는 복사 생성자가 있는 경우 컴파일러 생성 복사 생성자는 **const** `type`**&** 형식의 단일 인수를 수락합니다.  그렇지 않으면 컴파일러 생성 복사 생성자는 `type`**&** 형식의 단일 인수를 수락합니다.  
  
 생성자를 사용하여 **const** 또는 `volatile`을 초기화할 수 있으나 생성자 자체는 **const** 또는 `volatile`로 선언될 수 없습니다.  올바른 생성자 저장소 클래스는 **inline**뿐입니다. `__declspec` 키워드를 포함한 다른 모든 저장소 클래스 한정자를 생성자와 함께 사용하면 컴파일러 오류가 발생합니다.  
  
 stdcall 호출 규칙은 **\_\_stdcall** 키워드를 사용하여 선언된 정적 멤버 함수 및 전역 함수에 사용되며 가변 인수 목록은 사용하지 않습니다.  생성자와 같은 비정적 멤버 함수에서 **\_\_stdcall** 키워드를 사용할 경우 컴파일러에서 thiscall 호출 규칙을 사용합니다.  
  
 기본 클래스의 생성자는 파생 클래스에서 상속되지 않습니다.  파생 클래스 형식의 개체를 만들 때 해당 개체는 기본 클래스 구성 요소로 시작하여 생성된 후 파생 클래스 구성 요소로 이동합니다.  컴파일러는 완전한 개체의 해당 부분이 초기화될 때 각 기본 클래스의 생성자를 사용합니다\([기본 클래스 초기화](../misc/initializing-base-classes.md)에 설명된 가상 파생의 경우 제외\).  
  
##  <a name="explicitly_invoking_constructors"></a> 생성자를 명시적으로 호출  
 지정된 형식의 개체를 생성하기 위해 프로그램에서 생성자를 명시적으로 호출할 수 있습니다.  예를 들어, 줄의 끝을 설명하는 두 개의 `Point` 개체를 생성하려면 다음과 같은 코드를 작성합니다.  
  
```  
DrawLine( Point( 13, 22 ), Point( 87, 91 ) );  
```  
  
 `Point` 형식의 두 개체가 생성되어 `DrawLine` 함수로 전달되며 식의 끝에서 소멸됩니다\(함수 호출\).  
  
 생성자가 명시적으로 호출되는 대체 컨텍스트는 초기화에 있습니다.  
  
```  
Point pt = Point( 7, 11 );  
```  
  
 `Point` 형식의 개체는 `int` 형식의 두 인수를 허용하는 생성자를 사용하여 생성하고 초기화합니다.  
  
 앞의 두 예제에서와 같이 생성자를 명시적으로 호출하여 생성된 개체는 명명되지 않고 자신을 생성한 식의 수명을 갖습니다.  이에 대해서는 [임시 개체](../cpp/temporary-objects.md)에서 더욱 자세히 설명됩니다.  
  
 사용자 코드의 첫 번째 줄을 실행하기 전에 개체가 완전히 설정되었기 때문에\(가상 테이블 초기화 등이 완료됨\) 일반적으로 생성자 내에서 멤버 함수를 안전하게 호출할 수 있습니다.  그러나 생성이나 소멸 중에 멤버 함수에서 추상 기본 클래스에 대한 가상 멤버 함수를 호출하는 것은 안전하지 않을 수 있습니다.  
  
 생성자는 가상 함수를 호출할 수 있습니다.  가상 함수가 호출될 때 호출된 함수는 생성자의 자체 클래스\(또는 해당 기본 클래스에서 상속된 클래스\)에 대해 정의된 함수입니다.  다음 예제에서는 생성자 내에서 가상 함수가 호출될 때 발생하는 상황을 보여 줍니다.  
  
```  
// specl_calling_virtual_functions.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
class Base  
{  
public:  
    Base();             // Default constructor.  
    virtual void f();   // Virtual member function.  
};  
  
Base::Base()  
{  
    cout << "Constructing Base sub-object\n";  
    f();                // Call virtual member function  
}                       //  from inside constructor.  
  
void Base::f()  
{  
    cout << "Called Base::f()\n";  
}  
  
class Derived : public Base  
{  
public:  
    Derived();          // Default constructor.  
    void f();           // Implementation of virtual  
};                      //  function f for this class.  
  
Derived::Derived()  
{  
    cout << "Constructing Derived object\n";  
}  
  
void Derived::f()  
{  
    cout << "Called Derived::f()\n";  
}  
  
int main()  
{  
    Derived d;  
}  
```  
  
 위의 프로그램이 실행되면 `Derived d` 선언으로 인해 다음 순서대로 이벤트가 발생합니다.  
  
1.  `Derived` 클래스의 생성자\(`Derived::Derived`\)가 호출됩니다.  
  
2.  `Derived` 클래스의 생성자 본문에 진입하기 전에 `Base` 클래스의 생성자\(`Base::Base`\)가 호출됩니다.  
  
 `Base::Base`는 가상 함수인 `f` 함수를 호출합니다.  일반적으로 `Derived::f` 개체가 `d` 형식이기 때문에 `Derived`가 호출됩니다.  `Base::Base` 함수가 생성자이므로 개체는 아직 `Derived` 형식이 아니며, `Base::f`가 호출됩니다.  
  
## 참고 항목  
 [특수 멤버 함수](../misc/special-member-functions-cpp.md)