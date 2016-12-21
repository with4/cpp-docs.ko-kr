---
title: "new 연산자 (C++) | Microsoft Docs"
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
  - "new 키워드[C++]"
ms.assetid: 69fee812-1c28-4882-8fda-d1ad17860004
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# new 연산자 (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

사용 가능한 저장소에서 *type\-name*의 개체 또는 개체의 배열에 대한 메모리를 할당하고 적절한 형식의 0이 아닌 포인터를 개체에 반환합니다.  
  
> [!NOTE]
>  Microsoft C\+\+ 구성 요소 확장은 vtable 슬롯 항목을 추가하기 위해 `new` 키워드에 대한 지원을 제공합니다.  자세한 내용은 [new \(new slot in vtable\)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md)를 참조하세요.  
  
## 구문  
  
```  
[::] new [placement] new-type-name [new-initializer]  
[::] new [placement] ( type-name ) [new-initializer]  
```  
  
## 설명  
 실패할 경우 **new**는 0을 반환하거나 예외를 throw합니다. 자세한 내용은 [new 및 delete 연산자](../cpp/new-and-delete-operators.md)를 참조하세요.  사용자 지정 예외 처리 루틴을 작성하고 함수 이름을 인수로 사용하여 [\_set\_new\_handler](../c-runtime-library/reference/set-new-handler.md) 런타임 라이브러리 함수를 호출하면 이 기본 동작을 변경할 수 있습니다.  
  
 관리되는 힙에서 개체를 만드는 방법에 대한 자세한 내용은 [gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md)를 참조하세요.  
  
 **new**가 C\+\+ 클래스 개체에 메모리를 할당하는 데 사용되면 메모리가 할당된 후 개체의 생성자가 호출됩니다.  
  
 [new](../cpp/delete-operator-cpp.md) 연산자로 할당한 메모리를 할당 해제하려면 **delete** 연산자를 사용하세요.  
  
 다음 예제에서는 크기가 `dim`의 10배인 2차원 문자 배열을 할당한 다음 해제합니다.  다차원 배열을 할당할 때는 첫 번째를 제외한 모든 차원이 양수 값으로 계산되는 상수 식이어야 합니다. 맨 왼쪽 배열 차원은 양수 값으로 계산되는 임의의 식일 수 있습니다.  **new** 연산자를 사용하여 배열을 할당할 때는 첫 번째 차원이 0이 될 수 있습니다. **new** 연산자는 고유한 포인터를 반환합니다.  
  
```  
char (*pchar)[10] = new char[dim][10];  
delete [] pchar;  
```  
  
 *type\-name*은 **const**, `volatile`, 클래스 선언 또는 열거형 선언을 포함할 수 없습니다.  따라서 다음 식은 올바르지 않습니다.  
  
```  
volatile char *vch = new volatile char[20];  
```  
  
 참조 형식은 개체가 아니므로 **new** 연산자는 참조 형식을 할당하지 않습니다.  
  
 **new** 연산자를 사용하여 함수를 할당할 수 없지만 함수에 대한 포인터를 할당할 수는 있습니다.  다음 예제에서는 정수를 반환하는 함수에 대한 7개의 포인터 배열을 할당한 다음 해제합니다.  
  
```  
int (**p) () = new (int (*[7]) ());  
delete *p;  
```  
  
 추가 인수 없이 **new** 연산자를 사용하고 [\/GX](../build/reference/gx-enable-exception-handling.md), [\/EHa](../build/reference/eh-exception-handling-model.md) 또는 [\/EHs](../build/reference/eh-exception-handling-model.md) 옵션을 사용하여 컴파일하는 경우 생성자가 예외를 throw하면 컴파일러가 **delete** 연산자를 호출하기 위한 코드를 생성합니다.  
  
 다음 목록에서는 **new**의 문법 요소에 대해 설명합니다.  
  
 *placement*  
 **new**를 오버로드하는 경우 추가 인수를 전달하는 방법을 제공합니다.  
  
 *type\-name*  
 기본 제공 또는 사용자 정의 형식 중에서 할당할 형식을 지정합니다.  형식 사양이 복잡한 경우 괄호로 묶어 바인딩 순서를 강제로 지정할 수 있습니다.  
  
 *initializer*  
 초기화된 개체의 값을 제공합니다.  배열에 대한 이니셜라이저는 지정할 수 없습니다.  **new** 연산자는 클래스에 기본 생성자가 있는 경우에만 개체의 배열을 만듭니다.  
  
## 예제  
 다음 코드 예제는 문자 배열 및 `CName` 클래스 개체를 할당한 다음 해제합니다.  
  
```  
// expre_new_Operator.cpp  
// compile with: /EHsc  
#include <string.h>  
  
class CName {  
public:  
   enum {  
      sizeOfBuffer = 256  
   };  
  
   char m_szFirst[sizeOfBuffer];  
   char m_szLast[sizeOfBuffer];  
  
public:  
   void SetName(char* pszFirst, char* pszLast) {  
     strcpy_s(m_szFirst, sizeOfBuffer, pszFirst);  
     strcpy_s(m_szLast, sizeOfBuffer, pszLast);  
   }  
  
};  
  
int main() {  
   // Allocate memory for the array  
   char* pCharArray = new char[CName::sizeOfBuffer];  
   strcpy_s(pCharArray, CName::sizeOfBuffer, "Array of characters");  
  
   // Deallocate memory for the array  
   delete [] pCharArray;             
   pCharArray = NULL;  
  
   // Allocate memory for the object  
   CName* pName = new CName;  
   pName->SetName("Firstname", "Lastname");  
  
   // Deallocate memory for the object  
   delete pName;  
   pName = NULL;  
}  
```  
  
## 예제  
 할당 크기 이외의 인수가 포함된 형태인 **new** 연산자의 새 배치 형태를 사용하는 경우 생성자가 예외를 throw하면 컴파일러가 **delete** 연산자의 배치 형태를 지원하지 않습니다.  예:  
  
```  
// expre_new_Operator2.cpp  
// C2660 expected  
class A {  
public:  
   A(int) { throw "Fail!"; }  
};  
void F(void) {  
   try {  
      // heap memory pointed to by pa1 will be deallocated  
      // by calling ::operator delete(void*).  
      A* pa1 = new A(10);  
   } catch (...) {  
   }  
   try {  
      // This will call ::operator new(size_t, char*, int).  
      // When A::A(int) does a throw, we should call  
      // ::operator delete(void*, char*, int) to deallocate  
      // the memory pointed to by pa2.  Since  
      // ::operator delete(void*, char*, int) has not been implemented,  
      // memory will be leaked when the deallocation cannot occur.  
  
      A* pa2 = new(__FILE__, __LINE__) A(20);  
   } catch (...) {  
   }  
}  
  
int main() {  
   A a;  
}  
```  
  
## new로 할당된 개체 초기화  
 선택적 이니셜라이저 필드가 **new** 연산자의 문법에 포함되므로  사용자 정의 생성자를 사용하여 새 개체를 초기화할 수 있습니다.  초기화 수행 방법에 대한 자세한 내용은 [이니셜라이저](../cpp/initializers.md)를 참조하세요.  다음 예제에서는 **new** 연산자와 함께 초기화 식을 사용하는 방법을 보여 줍니다.  
  
```  
// expre_Initializing_Objects_Allocated_with_new.cpp  
class Acct  
{  
public:  
    // Define default constructor and a constructor that accepts  
    //  an initial balance.  
    Acct() { balance = 0.0; }  
    Acct( double init_balance ) { balance = init_balance; }  
private:  
    double balance;  
};  
  
int main()  
{  
    Acct *CheckingAcct = new Acct;  
    Acct *SavingsAcct = new Acct ( 34.98 );  
    double *HowMuch = new double ( 43.0 );  
    // ...  
}  
```  
  
 이 예제에서 `CheckingAcct` 개체가 **new** 연산자를 사용하여 할당되지만 기본 초기화가 지정되지 않습니다.  따라서 클래스의 기본 생성자인 `Acct()`가 호출됩니다.  그런 다음 명시적으로 34.98로 초기화된다는 점을 제외하고 `SavingsAcct` 개체가 같은 식으로 할당됩니다.  34.98은 **double** 형식이므로 초기화를 처리하기 위해 해당 형식의 인수를 사용하는 생성자가 호출됩니다.  마지막으로 비클래스 형식 `HowMuch`가 43.0으로 초기화됩니다.  
  
 개체가 클래스 형식이고 해당 클래스에 생성자\(이전 예제와 같음\)가 있으면 다음 조건 중 하나가 충족될 경우에만 **new** 연산자를 사용하여 개체를 초기화할 수 있습니다.  
  
-   이니셜라이저에 제공된 인수는 생성자의 인수와 일치합니다.  
  
-   클래스에 기본 생성자\(인수 없이 호출할 수 있는 생성자\)가 있습니다.  
  
 he constructors according to the rules set forth in `operator new`모호성 및 [특수 멤버 함수를 사용한 초기화](http://msdn.microsoft.com/ko-kr/0b399cab-40a7-4e79-9278-05f40139a0e1)에 명시된 규칙에 따라 [및 생성자에 대해 액세스 제어와 모호성 제어가 수행됩니다.](http://msdn.microsoft.com/ko-kr/82223d73-64cb-4923-b678-78f9568ff3ca)  
  
 **new** 연산자를 사용하여 배열을 할당할 때 요소마다 명시적으로 초기화할 수 없습니다. 기본 생성자만 호출됩니다\(있을 경우\).  자세한 내용은 [기본 인수](../cpp/default-arguments.md)를 참조하세요.  
  
 메모리 할당이 실패할 경우\(`operator new`가 0값 반환\) 초기화를 수행하지 않음으로써  존재하지 않는 데이터를 초기화하려는 시도를 막을 수 있습니다.  
  
 함수 호출과 마찬가지로 초기화된 식이 계산되는 순서가 정의되지 않습니다.  또한 메모리 할당을 수행하기 전에 완전히 계산되는 이 식에 의존하지 마세요.  메모리 할당이 실패하고 **new** 연산자가 0을 반환하면 이니셜라이저의 일부 식이 완전히 계산되지 않을 수도 있습니다.  
  
## new로 할당된 개체 수명  
 **new** 연산자를 사용하여 할당된 개체는 개체가 정의된 범위가 종료될 때 소멸되지 않습니다.  **new** 연산자는 해당 연산자가 할당한 개체의 포인터를 반환하기 때문에 이들 개체에 액세스하려면 프로그램에서 알맞은 범위의 포인터를 정의해야 합니다.  예:  
  
```  
// expre_Lifetime_of_Objects_Allocated_with_new.cpp  
// C2541 expected  
int main()  
{  
    // Use new operator to allocate an array of 20 characters.  
    char *AnArray = new char[20];  
  
    for( int i = 0; i < 20; ++i )  
    {  
        // On the first iteration of the loop, allocate  
        //  another array of 20 characters.  
        if( i == 0 )  
        {  
            char *AnotherArray = new char[20];  
        }  
    }  
  
    delete [] AnotherArray; // Error: pointer out of scope.  
    delete [] AnArray;      // OK: pointer still in scope.  
}  
```  
  
 `AnotherArray` 포인터가 예제 범위를 벗어나면 개체를 더 이상 삭제할 수 없습니다.  
  
## new 작동 방식  
 *new* 연산자가 포함된 식인 **allocation\-expression**은 다음 세 가지 작업을 수행합니다.  
  
-   할당할 개체에 대한 저장소를 찾고 예약합니다.  이 단계가 완료되면 올바른 양의 저장소가 할당되지만 아직 개체는 아닙니다.  
  
-   개체를 초기화합니다.  초기화가 완료되면 할당된 저장소가 개체가 되는 데 충분한 정보가 있습니다.  
  
-   *new\-type\-name* 또는 *type\-name*에서 파생된 포인터 형식의 개체에 대한 포인터를 반환합니다.  프로그램에서는 이 포인터를 사용하여 새로 할당된 개체에 액세스합니다.  
  
 **new** 연산자는 `operator new` 함수를 호출합니다.  모든 형식의 배열과 **class**, `struct` 또는 **union** 형식이 아닌 개체의 경우, 전역 함수인 **::operator new**가 저장소를 할당하기 위해 호출됩니다.  클래스 형식 개체는 클래스별로 고유한 `operator new` 정적 멤버 함수를 정의할 수 있습니다.  
  
 컴파일러에서는 `type` 형식의 개체를 할당하기 위한 **new** 연산자를 발견할 때 `type`**::operator new\( sizeof\(** `type` **\) \)**를 호출하거나, 사용자 정의 `operator new`가 정의되지 않은 경우 **::operator new\( sizeof\(** `type` **\) \)**를 호출합니다.  따라서 **new** 연산자는 개체에 대한 올바른 양의 메모리를 할당할 수 있습니다.  
  
> [!NOTE]
>  `operator new`에 대한 인수는 **size\_t** 형식입니다.  이 형식은 DIRECT.H, MALLOC.H, MEMORY.H, SEARCH.H, STDDEF.H, STDIO.H, STDLIB.H, STRING.H 및 TIME.H에서 정의됩니다.  
  
 문법에서 옵션을 사용하여 *placement*를 지정할 수 있습니다\([new 연산자](../cpp/new-operator-cpp.md)에 대한 문법 참조\).  *placement* 매개 변수는 `operator new`의 사용자 정의 구현에만 사용할 수 있습니다. 이 매개 변수를 사용하면 `operator new`에 추가 정보를 전달할 수 있습니다.  *와 같은 `T *TObject = new ( 0x0040 ) T;`placement* 필드가 포함된 식은 T 클래스에 멤버 operator new가 있으면 `T *TObject = T::operator new( sizeof( T ), 0x0040 );`로 변환되고, 그렇지 않으면 `T *TObject = ::operator new( sizeof( T ), 0x0040 );`로 변환됩니다.  
  
 *placement* 필드의 원래 용도는 하드웨어 종속 개체가 사용자 지정 주소에서 할당될 수 있도록 하는 것입니다.  
  
> [!NOTE]
>  위의 예제에서는 *placement* 필드에서 인수를 하나만 보여 주지만, 이런 식으로 `operator new`에 전달할 수 있는 추가 인수의 개수에는 제한이 없습니다.  
  
 `operator new`가 클래스 형식에 대해 정의되었더라도 다음 예제의 형태를 사용하여 전역 연산자를 사용할 수 있습니다.  
  
```  
T *TObject =::new TObject;  
```  
  
 범위 결정 연산자\(`::`\)는 강제로 전역 **new** 연산자를 사용하도록 합니다.  
  
## 참고 항목  
 [단항 연산자가 있는 식](../cpp/expressions-with-unary-operators.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)   
 [operator new 함수](../misc/operator-new-function.md)