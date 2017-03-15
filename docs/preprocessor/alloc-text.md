---
title: "alloc_text | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.alloc_text"
  - "alloc_text_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "alloc_text pragma"
  - "pragma, alloc_text"
ms.assetid: 1fd7be18-e4f7-4f70-b079-6326f72b871a
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# alloc_text
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정한 함수 정의가 상주하는 코드 섹션의 이름을 지정합니다.  pragma는 명명된 함수의 함수 선언자와 함수 정의 간에 발생해야 합니다.  
  
## 구문  
  
```  
  
#pragma alloc_text( "  
textsection  
", function1, ... )  
```  
  
## 설명  
 **alloc\_text** pragma에서는 C\+\+ 멤버 함수 또는 오버로드된 함수를 처리하지 않습니다.  Pragma는 C 링크로 선언된 함수, 즉, **extern "C"** 링크 사양으로 선언된 함수에만 적용됩니다.  C\+\+ 링크가 있는 함수에 pragma를 사용하려고 하면 컴파일러 오류가 발생합니다.  
  
 `__based`를 사용하여 함수 주소를 지정할 수 없으므로 **alloc\_text** pragma를 사용하여 섹션 위치를 지정해야 합니다.  *textsection*으로 지정된 이름은 큰따옴표로 묶어야 합니다.  
  
 **alloc\_text** pragma는 지정된 함수의 선언 뒤에, 그리고 해당 함수의 정의 앞에 표시되어야 합니다.  
  
 **alloc\_text** pragma에서 참조되는 함수는 pragma와 동일한 모듈에서 정의되어야 합니다.  이와 같이 수행되지 않고 정의되지 않은 함수가 나중에 다른 텍스트 섹션으로 컴파일되면 오류가 잡힐 수도 있고 안 될 수도 있습니다.  프로그램은 보통 올바르게 실행되더라도 함수는 원하는 섹션에서 할당되지 않습니다.  
  
 **alloc\_text**에 대한 다른 제한 사항은 다음과 같습니다.  
  
-   함수 내에서 사용할 수 없습니다.  
  
-   함수가 선언된 후, 그리고 함수가 정의되기 전에 사용되어야 합니다.  
  
## 참고 항목  
 [Pragma 지시문 및 \_\_Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)