---
title: 컴파일러 경고 (수준 1) C4291 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4291
dev_langs:
- C++
helpviewer_keywords:
- C4291
ms.assetid: c2b95dea-38f2-4609-9104-707c30798da4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c10351be640dc142f224cb5583a980e396f086cd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33282381"
---
# <a name="compiler-warning-level-1-c4291"></a>컴파일러 경고(수준 1) C4291
'declaration':를 찾을 수 없는 일치 하는 연산자 삭제 초기화는 예외를 throw 하는 경우 메모리를 해제 되지 않습니다.  
  
 배치 [새](../../cpp/new-operator-cpp.md) 사용 없음 배치 된에 대 한 [삭제](../../cpp/delete-operator-cpp.md)합니다.  
  
 연산자와 함께 개체에 대 한 메모리를 할당 하는 경우 **새**, 개체의 생성자에서 호출 됩니다. 생성자에서 예외를 throw 하는 개체에 할당 된 메모리를 할당 취소 합니다. 이렇게 하기 위해서는 연산자 **삭제** 연산자와 일치 하는 함수가 존재 **새**합니다.  
  
 연산자를 사용 하는 경우 **새** 추가 인수 없이 포함 된 컴파일을 [/GX](../../build/reference/gx-enable-exception-handling.md), [/EHs](../../build/reference/eh-exception-handling-model.md), 또는 예외 처리, 컴파일러를 사용 하도록 설정 하려면 /EHa 옵션에 코드를 생성 합니다 연산자를 호출 **삭제** 생성자에서 예외가 발생 합니다.  
  
 배치 형태를 사용 하는 경우는 **새** (크기 인수를 갖는 형태는 할당) 연산자와 개체의 생성자가 예외를 throw 컴파일러에서 연산자를호출하는코드를생성**삭제**; 것은 작업을 수행 하는 경우 연산자의 배치 형태 하지만 **삭제** 연산자의 배치 형태에 일치 하는 **새** 메모리를 할당 합니다. 예를 들어:  
  
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
  
 위의 예제에서는 경고가 발생 C4291 때문에 연산자의 배치 형태 없는 **삭제** 정의 된 연산자의 배치 형태를 일치 하는 **새**합니다. 이 문제를 해결 하려면 위에 다음 코드를 삽입 **주**합니다. 오버 로드 된 연산자의 모든 **삭제** 함수 매개 변수 값과 동일 오버 로드 된 연산자의 **새**, 첫 번째 매개 변수를 제외 하 고 있습니다.  
  
```  
void operator delete(void* pMem, char* pszFilename, int nLine)  
{  
   free(pMem);  
}  
```