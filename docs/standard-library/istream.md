---
title: "&lt; istream &gt; | Microsoft Docs"
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
  - "istream/std::<istream>"
  - "std.<istream>"
  - "<istream>"
  - "std::<istream>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "istream 헤더"
ms.assetid: efcf24e4-05d1-4719-ab0b-9e7ebe845d89
caps.latest.revision: 20
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt; istream &gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

iostreams에 대한 추출을 중재하는 템플릿 클래스 basic\_istream 및 삽입과 추출을 모두 중재하는 템플릿 클래스 basic\_iostream을 정의합니다. 헤더에서 관련 조작자도 정의합니다. 이 헤더 파일은 일반적으로 다른 iostreams 헤더에 의해 포함되며, 직접 포함해야 하는 경우는 거의 없습니다.  
  
## 구문  
  
```  
  
#include <istream>  
  
```  
  
### Typedefs  
  
|||  
|-|-|  
|[iostream](../Topic/iostream.md)|`char`에서 특수화된 `basic_iostream` 형식입니다.|  
|[istream](../Topic/istream.md)|`char`에서 특수화된 `basic_istream` 형식입니다.|  
|[wiostream](../Topic/wiostream.md)|**wchar**에서 특수화된 `basic_iostream` 형식입니다.|  
|[wistream](../Topic/wistream.md)|**wchar**에서 특수화된 `basic_istream` 형식입니다.|  
  
### 조작자  
  
|||  
|-|-|  
|[ws](../Topic/ws.md)|스트림의 공백을 건너뜁니다.|  
|[swap](../Topic/%3Cistream%3E%20swap.md)|두 스트림 개체를 교환합니다.|  
  
### 연산자  
  
|||  
|-|-|  
|[operator\>\>](../Topic/operator%3E%3E%20\(%3Cistream%3E\).md)|스트림에서 문자 및 문자열을 추출합니다.|  
  
### 클래스  
  
|||  
|-|-|  
|[basic\_iostream](../standard-library/basic-iostream-class.md)|입력과 출력을 둘 다 수행할 수 있는 스트림 클래스입니다.|  
|[basic\_istream](../standard-library/basic-istream-class.md)|이 템플릿 클래스는 문자 특성이 **Tr**\([traits\_type](../Topic/basic_ios::traits_type.md)이라고도 함\)에 의해 결정되는 **Elem**\([char\_type](../Topic/basic_ios::char_type.md)이라고도 함\) 형식의 요소가 있는 스트림 버퍼에서 요소 및 인코드된 개체의 추출을 제어하는 개체를 설명합니다.|  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream 프로그래밍](../standard-library/iostream-programming.md)   
 [iostreams 규칙](../standard-library/iostreams-conventions.md)