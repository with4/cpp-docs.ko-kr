---
title: "operator new(CRT) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr90.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
  - "msvcr110.dll"
  - "msvcr120.dll"
apitype: "DLLExport"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator new"
  - "스칼라 new"
ms.assetid: 4ae51618-a4e6-4172-b324-b99d86d1bdca
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# operator new(CRT)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

힙에서 메모리 블록을 할당합니다.  
  
## 구문  
  
```  
  
      void *__cdecl operator new(  
   size_t count  
);  
void *__cdecl operator new(  
   size_t count,   
   void * object  
) throw();  
void *__cdecl operator new(  
   size_t count,   
   const std::nothrow_t&  
) throw();  
```  
  
#### 매개 변수  
 *count*  
 할당 크기입니다.  
  
 *object*  
 개체가 생성된 메모리 블록을 가리키는 포인터입니다.  
  
## 반환 값  
 새로 할당된 저장소에서 가장 낮은 바이트 주소의 포인터입니다.  
  
## 설명  
 이러한 `operator new`의 형태는 벡터 new 형식\([연산자 new&#91;&#93;](../c-runtime-library/new-operator-crt.md)\)과는 다른 스칼라 new로 알려져 있습니다.  
  
 이 연산자의 첫 번째 형식은 비배치 형식으로 알려져 있습니다.  이 연산자의 두 번째 형식은 배치 형식이라고 하며, 세 번째 형식은 배치 형식이라고 하고, 세 번째 형태는 비투척, 배치 형태입니다.  
  
 이 연산자의 첫 번째 형식은 컴파일러에 의해 정의되고 new.h를 프로그램에 포함시킬 필요가 없습니다.  
  
 [delete 연산자](../c-runtime-library/operator-delete-crt.md)는 `operator new`로 할당된 메모리를 해제합니다.  
  
 new 연산자가 오류 상황에서 null을 반환하는지 예외를 발생시키는지를 구성할 수 있습니다.  자세한 내용은 [새 및 삭제 연산자](../cpp/new-and-delete-operators.md) 를 참조하십시오.  
  
 보고 혹은 보고하지 않는 동작의 예외에 대해, CRT `operator new`는 표준 C\+\+ 라이브러리의 [new 연산자](../Topic/operator%20new%20\(%3Cnew%3E\).md)처럼 동작합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|**new**|\<new.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
 다음은 스칼라, 비배치 형식의 `operator new`를 사용하는 방법을 보여줍니다.  
  
```  
// crt_new1.cpp  
#include <stdio.h>  
int main() {  
   int * i = new int(6);  
   printf("%d\n", *i);  
   delete i;  
}  
```  
  
 다음은 스칼라, 배치 형식의 `operator new`를 사용하는 방법을 보여줍니다.  
  
```  
// crt_new2.cpp  
#include <stdio.h>  
#include <new.h>  
int main() {  
   int * i = new int(12);  
   printf("*i = %d\n", *i);  
   // initialize existing memory (i) with, in this case, int(7)  
   int * j = new(i) int(7);   // placement new  
   printf("*j = %d\n", *j);  
   printf("*i = %d\n", *i);  
   delete i;   // or, could have deleted j  
}  
```  
  
 다음은 스칼라, 배치, 비투척 형식의 `operator new`를 사용하는 방법을 보여줍니다.  
  
```  
// crt_new3.cpp  
#include <stdio.h>  
#include <new.h>  
int main() {  
   // allocates memory, initialize (8) and if call fails, new returns null  
   int * k = new(std::nothrow) int(8);   // placement new  
   printf("%d\n", *k);  
   delete k;  
}  
```  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [메모리 할당](../c-runtime-library/memory-allocation.md)