---
title: "operator delete(CRT) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr90.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr120.dll"
  - "msvcr100.dll"
  - "msvcr80.dll"
apitype: "DLLExport"
f1_keywords: 
  - "delete[]"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "operator delete[]"
  - "벡터 delete"
ms.assetid: e91bd0df-3815-40ca-950a-67b470518aed
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# operator delete(CRT)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

할당된 블록을 해제합니다.  
  
## 구문  
  
```  
  
      void __cdecl operator delete[](void * object);  
void __cdecl operator delete[](void * object,   
   void * memory) throw();  
void __cdecl operator delete[](void * object,   
   const std::nothrow_t&) throw();  
```  
  
#### 매개 변수  
 *메모리*  
 해제된 메모리의 위치입니다.  
  
 *object*  
 삭제할 개체에 대한 포인터입니다.  
  
## 설명  
 **연산자 delete** 의 이러한 형태는 벡터 삭제이고, 스칼라 삭제 형태와 대비됩니다.\([연산자 delete&#91;&#93;](../c-runtime-library/operator-delete-crt.md)\).  
  
 **연산자** `delete[]` 는 [new 연산자](../c-runtime-library/new-operator-crt.md) 에 의해 할당된 메모리를 해제합니다.  
  
 이 연산자의 첫 번째 형식은 비배치 형식으로 알려져 있습니다.  연산자의 두번째와 세번째 형태는 공통적으로 코드로부터 호출되지 않지만, 배치에 실패했을때 컴파일러에 매칭되는 삭제를 제공하기 위해 존재합니다.  
  
 이 연산자의 첫 번째 형식은 컴파일러에 의해 정의되고 new.h를 프로그램에 포함시킬 필요가 없습니다.  
  
 보고 혹은 보고하지 않는 동작의 예외에 대해, CRT **연산자** `delete[]` 는 표준 C\+\+라이브러리에서 [delete 연산자](../Topic/operator%20delete\(%3Cnew%3E\).md) 처럼 동작합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`delete[]`|\<new.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
 연산자 **delete** 를 사용하는 예제에 대해 [new 연산자](../c-runtime-library/new-operator-crt.md) 를 참고하세요.  
  
## 참고 항목  
 [메모리 할당](../c-runtime-library/memory-allocation.md)