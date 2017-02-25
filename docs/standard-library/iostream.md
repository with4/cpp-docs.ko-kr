---
title: "&lt;iostream&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.<iostream>"
  - "std::<iostream>"
  - "<iostream>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "iostream 헤더"
ms.assetid: de5d39e1-7e77-4b55-bcd1-7c77b41515c8
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# &lt;iostream&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

표준 스트림에서 읽기 및 쓰기를 제어하는 개체를 선언합니다.  대체로 C\+\+ 프로그램에서 입력 및 출력을 수행하기 위해 포함해야 하는 유일한 헤더입니다.  
  
## 구문  
  
```  
  
#include <iostream>  
  
```  
  
## 설명  
 개체는 다음 두 그룹으로 나뉩니다.  
  
-   [cin](../Topic/cin.md), [cout](../Topic/cout.md), [cerr](../Topic/cerr.md) 및 [clog](../Topic/clog.md)는 바이트 지향적이며, 일반적인 바이트 단위 전송을 수행합니다.  
  
-   [wcin](../Topic/wcin.md), [wcout](../Topic/wcout.md), [wcerr](../Topic/wcerr.md) 및 [wclog](../Topic/wclog.md)는 와이드 지향적이며, 프로그램에서 내부적으로 조작하는 와이드 문자로\/에서 변환합니다.  
  
 표준 입력과 같은 스트림에서 특정 작업을 수행한 후에는 동일한 스트림에서 다른 방향의 작업을 수행할 수 없습니다.  따라서 예를 들어 프로그램이 [cin](../Topic/cin.md) 및 [wcin](../Topic/wcin.md) 둘 다에서 구분 없이 작동할 수 없습니다.  
  
 이 헤더에서 선언된 모든 개체는 특이한 속성을 공유합니다. \<iostream\>을 포함하는 변환 단위에서 정의한 정적 개체 앞에 생성된다고 가정할 수 있습니다.  마찬가지로, 정의한 해당 정적 개체에 대한 소멸자 이전에 이러한 개체가 소멸되지 않는다고 가정할 수 있습니다.  그러나 출력 스트림은 프로그램 종료 중에 플러시됩니다. 따라서 프로그램 시작 전과 프로그램 종료 후에 안전하게 표준 스트림에서 읽거나 쓸 수 있습니다.  
  
 그러나 이 보장은 범용이 아닙니다.  정적 생성자는 다른 변환 단위에서 함수를 호출할 수 있습니다.  호출된 함수는 변환 단위가 정적 구성에 참여하는 불확실한 순서를 감안할 때 이 헤더에 선언된 개체가 생성되었다고 가정할 수 없습니다.  이러한 컨텍스트에서 해당 개체를 사용하려면 먼저 [ios\_base:: init](../Topic/ios_base::Init.md) 클래스의 개체를 생성해야 합니다.  
  
### 전역 스트림 개체  
  
|||  
|-|-|  
|[cerr](../Topic/cerr.md)|`cerr` 전역 스트림을 지정합니다.|  
|[cin](../Topic/cin.md)|`cin` 전역 스트림을 지정합니다.|  
|[clog](../Topic/clog.md)|`clog` 전역 스트림을 지정합니다.|  
|[cout](../Topic/cout.md)|`cout` 전역 스트림을 지정합니다.|  
|[wcerr](../Topic/wcerr.md)|`wcerr` 전역 스트림을 지정합니다.|  
|[wcin](../Topic/wcin.md)|`wcin` 전역 스트림을 지정합니다.|  
|[wclog](../Topic/wclog.md)|`wclog` 전역 스트림을 지정합니다.|  
|[wcout](../Topic/wcout.md)|`wcout` 전역 스트림을 지정합니다.|  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream 프로그래밍](../standard-library/iostream-programming.md)   
 [iostreams 규칙](../standard-library/iostreams-conventions.md)