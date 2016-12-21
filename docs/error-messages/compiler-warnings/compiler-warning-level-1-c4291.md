---
title: "컴파일러 경고 (수준 1) C4291 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4291"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4291"
ms.assetid: c2b95dea-38f2-4609-9104-707c30798da4
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4291
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'declaration' : 일치하는 delete 연산자가 없습니다. 초기화할 때 예외가 Throw되지 않으면 메모리가 확보되지 않습니다.  
  
 [new](../../cpp/new-operator-cpp.md)를 [delete](../../cpp/delete-operator-cpp.md)가 없는 상태에서 사용했습니다.  
  
 **new** 연산자를 사용하여 개체에 메모리가 할당될 때 개체의 생성자가 호출됩니다.  생성자가 예외를 throw하면 개체에 할당된 모든 메모리는 할당 취소되어야 합니다.  이렇게 하기 위해서는 **new** 연산자에 일치하는 **delete** 연산자 함수가 있어야 합니다.  
  
 **new** 연산자를 추가 인수 없이 사용한 상태에서 [\/GX](../../build/reference/gx-enable-exception-handling.md), [\/EH](../../build/reference/eh-exception-handling-model.md) 또는 \/EHa 옵션을 통해 컴파일하여 예외 처리를 가능하게 만들면 생성자가 예외를 throw한 경우 컴파일러에서 **delete** 연산자를 호출하기 위한 코드를 생성합니다.  
  
 할당 크기와 인수를 사용하는 **new** 연산자의 배치 형식을 사용한 상태에서 개체의 생성자가 예외를 throw하면 컴파일러에서 **delete** 연산자를 호출하기 위한 코드를 생성합니다. 그러나 이러한 작업은 **delete** 연산자의 배치 형식이 메모리를 할당한 **new** 연산자의 배치 형식에 일치하는 경우에만 이루어집니다.  예를 들면 다음과 같습니다.  
  
```  
// C4291.cpp  
// compile with: /EHsc /W1  
#include <malloc.h>  
  
class CList  
{  
public:  
   CList(int)  
   {  
      throw "Fail!";  
   }  
};  
  
void* operator new(size_t size, char* pszFilename, int nLine)  
{  
   return malloc(size);  
}  
  
int main(void)  
{  
   try  
   {  
      // This will call ::operator new(unsigned int) to allocate heap  
      // memory. Heap memory pointed to by pList1 will automatically be  
      // deallocated by a call to ::operator delete(void*) when  
      // CList::CList(int) throws an exception.  
      CList* pList1 = new CList(10);  
   }  
   catch (...)  
   {  
   }  
  
   try  
   {  
      // This will call the overloaded ::operator new(size_t, char*, int)  
      // to allocate heap memory. When CList::CList(int) throws an  
      // exception, ::operator delete(void*, char*, int) should be called  
      // to deallocate the memory pointed to by pList2. Since  
      // ::operator delete(void*, char*, int) has not been implemented,  
      // memory will be leaked when the deallocation cannot occur.  
      CList* pList2 = new(__FILE__, __LINE__) CList(20);   // C4291  
   }  
   catch (...)  
   {  
   }  
}  
```  
  
 위의 예제에서는 **new** 연산자의 배치 형식에 일치하는 **delete** 연산자의 배치 형식을 정의하지 않았으므로 C4291 경고가 발생합니다.  이 문제를 해결하려면 다음 코드를 **main** 위에 넣으십시오.  다음 코드에서는 첫 번째 매개 변수를 제외한 모든 오버로드된 **delete** 연산자의 함수 매개 변수가 오버로드된 **new** 연산자의 함수 매개 변수와 일치합니다.  
  
```  
void operator delete(void* pMem, char* pszFilename, int nLine)  
{  
   free(pMem);  
}  
```