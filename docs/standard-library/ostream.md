---
title: "&lt;ostream&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.<ostream>"
  - "<ostream>"
  - "ostream/std::<ostream>"
  - "std::<ostream>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ostream 헤더"
ms.assetid: 90c3b6fb-57cd-4ae7-99b8-8512f24a67d2
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# &lt;ostream&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

iostreams에 대한 삽입을 중재하는 템플릿 클래스 [basic\_ostream](../standard-library/basic-ostream-class.md)을 정의합니다.  헤더에서 여러 관련 조작자도 정의합니다.  이 헤더는 일반적으로 다른 iostreams 헤더에 의해 포함되며,  직접 포함해야 하는 경우는 거의 없습니다.  
  
## 구문  
  
```  
  
#include <ostream>  
  
```  
  
### Typedefs  
  
|||  
|-|-|  
|[ostream](../Topic/ostream.md)|`char`에서 특수화된 `basic_ostream` 및 `char`에서 특수화된 `char_traits`를 통해 형식을 만듭니다.|  
|[wostream](../Topic/wostream.md)|`wchar_t`에서 특수화된 `basic_ostream` 및 `wchar_t`에서 특수화된 `char_traits`를 통해 형식을 만듭니다.|  
  
### 조작자  
  
|||  
|-|-|  
|[endl](../Topic/endl.md)|줄을 종료하고 버퍼를 플러시합니다.|  
|[끝](../Topic/ends%20\(Standard%20C++%20Library\).md)|문자열을 종료합니다.|  
|[flush](../Topic/flush%20\(Standard%20C++%20Library\).md)|버퍼를 플러시합니다.|  
||왼쪽 `basic_ostream` 개체 매개 변수의 값을 오른쪽 `basic_ostream` 개체 매개 변수의 값으로 교환합니다.|  
  
### 운영자  
  
|||  
|-|-|  
|[연산자 \<\<](../Topic/operator%3C%3C%20\(%3Costream%3E\).md)|스트림에 다양한 형식을 씁니다.|  
  
### 클래스  
  
|||  
|-|-|  
|[basic\_ostream](../standard-library/basic-ostream-class.md)|이 템플릿 클래스는 스트림 버퍼에 요소 및 인코드된 개체 삽입을 제어하는 개체를 설명합니다.|  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream 프로그래밍](../standard-library/iostream-programming.md)   
 [iostreams 규칙](../standard-library/iostreams-conventions.md)