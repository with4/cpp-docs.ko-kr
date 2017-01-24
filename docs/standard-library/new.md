---
title: "&lt;new&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::<new>"
  - "<new>"
  - "std.<new>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "new 헤더"
ms.assetid: 218e2a15-34e8-4ef3-9122-1e90eccf8559
caps.latest.revision: 18
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;new&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

프로그램이 제어하는 저장소의 할당 및 해제를 제어하는 여러 형식 및 함수를 정의합니다.  또한 저장소 관리 오류에 대한 보고를 위해 구성 요소를 정의합니다.  
  
## 구문  
  
```  
  
#include <new>  
  
```  
  
## 설명  
 이 헤더에 선언된 함수 중 일부는 교체할 수 있습니다.  구현은 이 문서에서 해당 동작을 설명하는 기본 버전을 제공합니다.  그러나 프로그램에서 동일한 서명으로 함수를 정의하여 링크 타임에 기본 버전을 바꿀 수 있습니다.  대체 버전은 이 문서에 설명된 요구 사항을 충족해야 합니다.  
  
### 개체  
  
|||  
|-|-|  
|[nothrow](../Topic/nothrow%20\(%3Cnew%3E\).md)|**new** 및 **delete**의 `nothrow` 버전에 대한 인수로 사용할 개체를 제공합니다.|  
  
### Typedefs  
  
|||  
|-|-|  
|[new\_handler](../Topic/new_handler.md)|새 처리기로 사용하기에 적합한 함수를 가리키는 형식입니다.|  
  
### Functions  
  
|||  
|-|-|  
|[set\_new\_handler](../Topic/set_new_handler.md)|new가 메모리 할당 시도에 실패할 때 호출되는 사용자 함수를 설치합니다.|  
  
### 운영자  
  
|||  
|-|-|  
|[operator delete](../Topic/operator%20delete%20\(%3Cnew%3E\).md)|개별 개체에 대해 저장소를 할당 해제하기 위해 delete 식에서 호출되는 함수입니다.|  
|[operator delete&#91;&#93;](../Topic/operator%20delete\(%3Cnew%3E\).md)|개체 배열에 대해 저장소를 할당 해제하기 위해 delete 식에서 호출되는 함수입니다.|  
|[operator new](../Topic/operator%20new%20\(%3Cnew%3E\).md)|개별 개체에 대해 저장소를 할당하기 위해 new 식에서 호출되는 함수입니다.|  
|[operator new&#91;&#93;](../Topic/operator%20new\(%3Cnew%3E\).md)|개체 배열에 대해 저장소를 할당하기 위해 new 식에서 호출되는 함수입니다.|  
  
### 클래스  
  
|||  
|-|-|  
|[bad\_alloc 클래스](../standard-library/bad-alloc-class.md)|이 클래스는 할당 요청이 성공하지 못했음을 나타내기 위해 발생하는 예외를 설명합니다.|  
|[nothrow\_t 클래스](../standard-library/nothrow-t-structure.md)|이 클래스는 함수가 예외를 발생시키는 대신 null 포인터를 반환하여 할당 오류를 보고해야 함을 나타내기 위해 new 연산자에 대한 함수 매개 변수로 사용됩니다.|  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)