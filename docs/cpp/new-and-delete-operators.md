---
title: "new 및 delete 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "delete_cpp"
  - "new_cpp"
  - "new"
  - "delete"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "delete 키워드[C++], 구문"
  - "new 키워드[C++], 개체의 동적 할당"
  - "nothrownew.obj"
ms.assetid: fa721b9e-0374-4f04-bb87-032ea775bcc8
caps.latest.revision: 16
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# new 및 delete 연산자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+에서는 [new](../cpp/new-operator-cpp.md) 및 [delete](../cpp/delete-operator-cpp.md) 연산자를 사용하여 개체의 동적 할당 및 할당 해제를 지원합니다.  이러한 연산자는 사용 가능한 저장소라고 하는 풀에서 개체에 대한 메모리를 할당합니다.  `new` 연산자는 [operator new](../misc/operator-new-function.md) 특수 함수를 호출하고, `delete` 연산자는 [operator delete](../misc/operator-delete-function.md) 특수 함수를 호출합니다.  
  
 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] .NET 2002에서 표준 C\+\+ 라이브러리의 `new` 함수는 C\+\+ 표준에서 지정된 동작, 즉 메모리 할당이 실패하는 경우 std::bad\_alloc 예외를 throw하는 동작을 지원합니다.  
  
 C 런타임 라이브러리의 `new` 함수도 메모리 할당이 실패하는 경우 std::bad\_alloc 예외를 throw합니다.  
  
 C 런타임 라이브러리의 throw하지 않는 `new` 버전을 원하는 경우 프로그램을 nothrownew.obj와 연결합니다.  하지만 nothrownew.obj와 연결하면 표준 C\+\+ 라이브러리의 `new`가 더 이상 작동하지 않습니다.  
  
 C 런타임 라이브러리와 표준 C\+\+ 라이브러리를 구성하는 라이브러리 파일의 목록은 [CRT 라이브러리 기능](../c-runtime-library/crt-library-features.md)를 참조하세요.  
  
## new 연산자  
 프로그램에서 다음과 같은 문이 발견될 경우, `operator new` 함수가 호출됩니다.  
  
```  
char *pch = new char[BUFFER_SIZE];  
```  
  
 저장소의 0바이트가 요청될 경우 **operator new**는 명확한 개체 포인터를 반환합니다. 즉, **operator new**에 대한 반복 호출을 통해 다른 포인터를 반환합니다.  할당 요청을 위한 충분한 메모리가 없을 경우 **operator new**는 **NULL**을 반환하거나 예외를 발생시킵니다. 자세한 내용은 [new 및 delete 연산자](../cpp/new-and-delete-operators.md)를 참조하세요.  
  
 여유 메모리를 확보하는 루틴을 작성한 다음 할당을 다시 시도할 수도 있습니다. 자세한 내용은 [\_set\_new\_handler](../c-runtime-library/reference/set-new-handler.md)를 참고하세요.  복구 체계에 대한 자세한 내용은 다음 항목, [부족한 메모리 조건 처리](../misc/handling-insufficient-memory-conditions.md)를 참조하세요.  
  
 다음 표에는 `operator new` 함수의 두 범위가 설명되어 있습니다.  
  
### operator new 함수의 범위  
  
|연산자|범위|  
|---------|--------|  
|**::operator new**|전역|  
|*class\-name* **::operator new**|클래스|  
  
 **operator new**의 첫 번째 인수는 **size\_t** 형식\(STDDEF.H에 정의된 형식\)이어야 하며 반환 형식은 항상 **void \***입니다.  
  
 전역 **operator new** 함수를 사용하여 **new** 연산자가 기본 제공 형식의 개체, 즉 사용자 정의된 **operator new** 함수를 포함하지 않는 클래스 형식의 개체 및 모든 형식의 배열을 할당할 때 호출됩니다.  **new** 연산자를 사용하여 클래스 형식의 개체를 **operator new**가 정의되는 지점에 할당할 때 클래스의 **operator new**가 호출됩니다.  
  
 클래스에 대해 정의된 **operator new** 함수는 해당 클래스 형식 개체의 전역 **operator new** 함수를 숨기는 정적 멤버 함수입니다\(가상은 될 수 없음\).  메모리를 지정된 값에 할당하고 설정하기 위해 **new** 연산자가 사용되는 경우를 다음의 예제를 통해 살펴보세요.  
  
```  
// spec1_the_operator_new_function1.cpp  
#include <malloc.h>  
#include <memory.h>  
  
class Blanks  
{  
public:  
    Blanks(){}  
    void *operator new( size_t stAllocateBlock, char chInit );  
};  
void *Blanks::operator new( size_t stAllocateBlock, char chInit )  
{  
    void *pvTemp = malloc( stAllocateBlock );  
    if( pvTemp != 0 )  
        memset( pvTemp, chInit, stAllocateBlock );  
    return pvTemp;  
}  
// For discrete objects of type Blanks, the global operator new function  
// is hidden. Therefore, the following code allocates an object of type  
// Blanks and initializes it to 0xa5  
int main()  
{  
   Blanks *a5 = new(0xa5) Blanks;  
   return a5 != 0;  
}  
```  
  
 **new**의 괄호 안 인수는 `Blanks::operator new` 인수로서 `chInit`에 전달됩니다.  그러나 전역 **operator new** 함수가 숨겨져 있기 때문에 다음과 같은 오류를 생성하는 코드가 발생할 수 있습니다.  
  
```  
Blanks *SomeBlanks = new Blanks;  
```  
  
 Visual C\+\+ 5.0 이전 버전에서 **new** 연산자를 통해 할당된 비클래스 형식 및 모든 배열\(**클래스** 형식인지 여부에 관계없음\)은 항상 전역 **operator new** 함수를 사용했습니다.  
  
 Visual C\+\+ 5.0 이후부터 컴파일러는 클래스 선언에서 멤버 배열, **new** 및 **delete** 연산자를 지원합니다.  예:  
  
```  
// spec1_the_operator_new_function2.cpp  
class MyClass  
{  
public:  
   void * operator new[] (size_t)  
   {  
      return 0;  
   }  
   void   operator delete[] (void*)  
   {  
   }  
};  
  
int main()   
{  
   MyClass *pMyClass = new MyClass[5];  
   delete [] pMyClass;  
}  
```  
  
### 메모리 부족 처리  
 다음과 같이 실패한 메모리 할당에 대한 테스트를 수행할 수 있습니다.  
  
```  
// insufficient_memory_conditions.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
#define BIG_NUMBER 100000000  
int main() {  
   int *pI = new int[BIG_NUMBER];  
   if( pI == 0x0 ) {  
      cout << "Insufficient memory" << endl;  
      return -1;  
   }  
}  
```  
  
 실패한 메모리 할당 요청을 처리하는 또 다른 방법은, 이러한 오류를 처리하는 사용자 지정 복구 루틴을 작성한 후, [\_set\_new\_handler](../c-runtime-library/reference/set-new-handler.md) 런타임 함수를 요청하여 함수를 등록하는 것입니다.  
  
## delete 연산자  
 **new** 연산자를 사용하여 동적으로 할당되는 메모리는 **delete** 연산자를 사용하여 비울 수 있습니다.  delete 연산자는 **operator delete** 함수를 호출합니다. 이 함수는 메모리를 사용 가능한 풀로 다시 비웁니다.  **delete** 연산자를 사용하면 클래스 소멸자\(있을 경우\)도 호출됩니다.  
  
 전역 및 클래스 범위의 **operator delete** 함수가 있습니다.  하나의 **operator delete** 함수만 특정 클래스에 대해 정의할 수 있으며, 정의하는 경우 전역 **operator delete** 함수가 숨겨집니다.  전역 **operator delete** 함수는 항상 모든 형식의 배열에 대해 호출됩니다.  
  
 전역 **operator delete** 함수는 선언되는 경우 할당 해제할 개체에 대한 포인터를 포함하는 **void \*** 형식의 단일 인수를 사용합니다.  반환 형식은 `void`입니다\(**operator delete**는 값을 반환할 수 없음\).  클래스 멤버 **operator delete** 함수에는 두 가지 형태가 있습니다.  
  
```  
void operator delete( void * );  
void operator delete( void *, size_t );  
```  
  
 앞의 두 변형 형태 중 하나만 특정 클래스에 있을 수 있습니다.  첫 번째 형태는 전역 `operator delete`에 대해 설명한 대로 작동합니다.  두 번째 형태에는 두 개의 인수가 사용됩니다. 첫 번째 인수는 할당 해제할 메모리 블록에 대한 포인터이고 두 번째 인수는 할당 해제할 바이트 수입니다.  두 번째 형태는 기본 클래스의 **operator delete** 함수를 사용하여 파생 클래스의 개체를 삭제할 때 특히 유용합니다.  
  
 **operator delete** 함수는 정적입니다. 따라서 가상일 수 없습니다.  `operator delete` 함수는 [멤버 액세스 제어](../cpp/member-access-control-cpp.md)에 설명된 대로 액세스 제어를 따릅니다.  
  
 다음 예제에서는 메모리의 할당 및 할당 해제를 기록하기 위해 설계된 사용자 정의 **operator new** 및 **operator delete** 함수를 보여 줍니다.  
  
```  
// spec1_the_operator_delete_function1.cpp  
// compile with: /EHsc  
// arguments: 3  
#include <iostream>  
using namespace std;  
  
int fLogMemory = 0;      // Perform logging (0=no; nonzero=yes)?  
int cBlocksAllocated = 0;  // Count of blocks allocated.  
  
// User-defined operator new.  
void *operator new( size_t stAllocateBlock ) {  
   static int fInOpNew = 0;   // Guard flag.  
  
   if ( fLogMemory && !fInOpNew ) {  
      fInOpNew = 1;  
      clog << "Memory block " << ++cBlocksAllocated  
          << " allocated for " << stAllocateBlock  
          << " bytes\n";  
      fInOpNew = 0;  
   }  
   return malloc( stAllocateBlock );  
}  
  
// User-defined operator delete.  
void operator delete( void *pvMem ) {  
   static int fInOpDelete = 0;   // Guard flag.  
   if ( fLogMemory && !fInOpDelete ) {  
      fInOpDelete = 1;  
      clog << "Memory block " << cBlocksAllocated--  
          << " deallocated\n";  
      fInOpDelete = 0;  
   }  
  
   free( pvMem );  
}  
  
int main( int argc, char *argv[] ) {  
   fLogMemory = 1;   // Turn logging on  
   if( argc > 1 )  
      for( int i = 0; i < atoi( argv[1] ); ++i ) {  
         char *pMem = new char[10];  
         delete[] pMem;  
      }  
   fLogMemory = 0;  // Turn logging off.  
   return cBlocksAllocated;  
}  
```  
  
 앞의 코드를 사용하여 "메모리 누수"를 검색할 수 있습니다. 메모리 누수는 사용 가능한 저장소에 할당되었지만 비워지지 않은 메모리를 의미합니다.  이 검색 작업을 수행하기 위해 메모리의 할당 및 할당 해제 횟수를 셀 수 있도록 전역 **new** 및 **delete** 연산자가 다시 정의됩니다.  
  
 Visual C\+\+ 5.0 이후부터 컴파일러는 클래스 선언에서 멤버 배열, **new** 및 **delete** 연산자를 지원합니다.  예:  
  
```  
// spec1_the_operator_delete_function2.cpp  
// compile with: /c  
class X  {  
public:  
   void * operator new[] (size_t) {  
      return 0;  
   }  
   void operator delete[] (void*) {}  
};  
  
void f() {  
   X *pX = new X[5];  
   delete [] pX;  
}  
```  
  
## 참고 항목  
 [특수 멤버 함수](../misc/special-member-functions-cpp.md)