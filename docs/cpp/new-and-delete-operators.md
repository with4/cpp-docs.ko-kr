---
title: "새 및 delete 연산자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- delete_cpp
- new
dev_langs:
- C++
helpviewer_keywords:
- new keyword [C++], dynamic allocation of objects
- nothrownew.obj
- delete keyword [C++], syntax
ms.assetid: fa721b9e-0374-4f04-bb87-032ea775bcc8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3af862988502ac0d1908c466aae5e62b753509c2
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2018
---
# <a name="new-and-delete-operators"></a>new 및 delete 연산자

C + +에서는 동적 할당 및 개체를 사용 하 여 할당 취소는 [새](../cpp/new-operator-cpp.md) 및 [삭제](../cpp/delete-operator-cpp.md) 연산자입니다. 이러한 연산자는 사용 가능한 저장소라고 하는 풀에서 개체에 대한 메모리를 할당합니다. `new` 특수 함수를 호출 하는 연산자 [new 연산자](../cpp/new-operator-cpp.md), 및 `delete` 특수 함수를 호출 하는 연산자 [delete 연산자](../cpp/delete-operator-cpp.md)합니다.  
  
 `new` c + + 표준 라이브러리의 함수는 메모리 할당에 실패 하는 경우 std:: bad_alloc 예외를 throw 하는 c + + 표준에 지정 된 동작을 지원 합니다. Throw 되지 않는 버전의 원하는 경우 `new`, 프로그램을 nothrownew.obj와 연결 합니다. 그러나을 연결할 때 기본 nothrownew.obj와 연결 `operator new` c + + 표준 라이브러리의 함수가 더 이상.  
  
 C 런타임 라이브러리 및 c + + 표준 라이브러리를 구성 하는 라이브러리 파일의 목록에 대 한 참조 [CRT 라이브러리 기능](../c-runtime-library/crt-library-features.md)합니다.  
  
##  <a id="new_operator"> </a> New 연산자  
 프로그램에서 다음과 같은 문이 발견될 경우, `operator new` 함수가 호출됩니다.  
  
```cpp  
char *pch = new char[BUFFER_SIZE];  
```  
  
저장소의 0 바이트에 대 한 요청인 경우 **new 연산자** 고유 개체에 대 한 포인터를 반환 (즉, 반복 호출을 **new 연산자** 다른 포인터를 반환). 할당 요청에 대 한 메모리가 부족 한 경우 **new 연산자** std:: bad_alloc 예외를 throw 하거나 반환 **nullptr** throw 되지 않는에 연결 하면 `operator new` 지원 합니다.  
  
메모리를 해제 하 고; 할당을 다시 시도 하려고 하는 루틴을 작성할 수 있습니다. 참조 [_set_new_handler](../c-runtime-library/reference/set-new-handler.md) 자세한 정보에 대 한 합니다. 복구 체계에 대 한 자세한 내용은이 항목의 처리 메모리가 부족 하 여 섹션을 참조 합니다.  

  
다음 표에는 `operator new` 함수의 두 범위가 설명되어 있습니다.  
  
### <a name="scope-for-operator-new-functions"></a>operator new 함수의 범위  
  
|연산자|범위|  
|--------------|-----------|  
|**:: new 연산자**|Global|  
|*class-name* **::operator new**|클래스|  
  
 첫 번째 인수 **new 연산자** 형식 이어야 합니다 **size_t** (에 정의 된 형식 \<stddef.h >), 하며 반환 형식은 항상 **void \***  .  
  
 전역 **new 연산자** 함수 때 호출 되는 **새** 기본 제공 형식의 개체를 할당 연산자가 사용, 클래스 형식 개체의 포함 하지 않는 사용자 정의 **new 연산자** 함수 및 모든 종류의 배열입니다. 때는 **새** 클래스 형식의 개체를 할당 연산자를 사용 하는 위치는 **new 연산자** 정의 된 해당 클래스의 **new 연산자** 호출 됩니다.  
  
 **new 연산자** 클래스는 전역 숨기는 정적 멤버 함수 (바이트일 수는 없습니다 따라서 가상)에 대해 정의 된 함수 **new 연산자** 해당 클래스 형식의 개체에 대 한 함수입니다. 경우 여기서 **새** 할당 하 고 지정된 된 값에 메모리를 설정 하는 데 사용 됩니다.  
  
```cpp  
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
  
 괄호 안 인수 **새** 에 전달 `Blanks::operator new` 로 `chInit` 인수입니다. 그러나 전역 **new 연산자** 함수가 숨겨져 오류가 발생 하는 다음과 같은 코드:  
  
```cpp  
Blanks *SomeBlanks = new Blanks;  
```  
  
 Visual c + + 5.0 및 이전 버전, 비 클래스 형식 및 모든 배열 (의 인지 여부에 관계 없이 **클래스** 유형) 사용 하 여 할당 된 **새** 연산자는 항상 전역 사용 **new 연산자** 함수입니다.  
  
 Visual c + + 5.0 이후부터, 컴파일러 지원 멤버 배열을 **새** 및 **삭제** 연산자 클래스 선언에 있습니다. 예를 들어:  
  
```cpp  
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
  
### <a name="handling-insufficient-memory"></a>메모리 부족 처리  
 다음과 같이 실패한 메모리 할당에 대한 테스트를 수행할 수 있습니다.  
  
```cpp  
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
  
 실패 한 메모리 할당 요청을 처리 하는 다른 방법으로: 이러한 오류를 처리 하는 사용자 지정 복구 루틴을 작성 한 다음 함수를 호출 하 여 등록는 [_set_new_handler](../c-runtime-library/reference/set-new-handler.md) 런타임 함수입니다.  
  
##  <a id="delete_operator"> </a> Delete 연산자  
 사용 하 여 동적으로 할당 된 메모리는 **새** 연산자를 사용 하 여 해제할 수는 **삭제** 연산자입니다. Delete 연산자 호출은 **delete 연산자** 함수 메모리 사용 가능한 풀으로 해제 합니다. 사용 하는 **삭제** 연산자 또한를 사용 하면 클래스 소멸자 (있을 경우)를 호출할 수 있습니다.  
  
 전역 및 클래스 범위의 **delete 연산자** 함수입니다. 하나의 **delete 연산자** 지정된 된 클래스에 대 한 함수를 정의할 수 있습니다; 전역 숨깁니다을 정의한 경우 속성이 **delete 연산자** 함수입니다. 전역 **delete 연산자** 함수는 항상 모든 형식의 배열에 대 한 호출 됩니다.  
  
 전역 **delete 연산자** 함수입니다. 두 가지 형태가 있습니다 전역 **delete 연산자** 및 클래스 멤버 **delete 연산자** 함수:  
  
```cpp  
void operator delete( void * );  
void operator delete( void *, size_t );  
```  
  
 위의 두 가지 형태 중 하나만 지정된 된 클래스에 사용할 수 있습니다. 형식의 단일 인수를 사용 하는 첫 번째 형태는 **void \***를 할당 해제할 개체에 포인터를 포함 합니다. 두 번째 형태-할당 취소 크기의-는 두 개의 인수는 첫 번째 할당 해제할 메모리 블록에 대 한 포인터가 고 중 두 번째 할당 해제할 바이트 수입니다. 두 가지 양식의 반환 형식이 `void` (**delete 연산자** 값을 반환할 수 없습니다).  
  
 두 번째 폼의 목적은 삭제 될 개체의 정확한 크기 범주에 대 한 검색을 하지 않는 자체 할당에 가깝게 저장 되 고 캐시 가능성이 해제; 속도를입니다. 두 번째 형태는 특히 유용 프로그램 **delete 연산자** 기본 클래스에서 함수는 파생된 클래스의 개체를 삭제 하는 데 사용 됩니다.  
  
 **delete 연산자** 함수는 정적입니다; 따라서 가상 일 수 없습니다. `operator delete` 함수에 설명 된 대로 액세스 제어를 따릅니다 [멤버 액세스 제어](../cpp/member-access-control-cpp.md)합니다.  
  
 다음 예제에서는 사용자 정의 **new 연산자** 및 **delete 연산자** 할당 및 메모리 할당 해제를 기록 하도록 디자인 된 함수:  
  
```cpp  
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
  
 앞의 코드를 사용하여 "메모리 누수"를 검색할 수 있습니다. 메모리 누수는 사용 가능한 저장소에 할당되었지만 비워지지 않은 메모리를 의미합니다. 전역이 검색을 수행 하려면 **새** 및 **삭제** 연산자 count 할당 및 메모리 할당 취소 하도록 다시 정의 됩니다.  
  
 Visual c + + 5.0 이후부터, 컴파일러 지원 멤버 배열을 **새** 및 **삭제** 연산자 클래스 선언에 있습니다. 예를 들어:  
  
```cpp  
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

