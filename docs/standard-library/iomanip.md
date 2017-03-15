---
title: "&lt; iomanip &gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "iomanip/std::<iomanip>"
  - "std::<iomanip>"
  - "<iomanip>"
  - "std.<iomanip>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "iomanip 헤더"
ms.assetid: 3681c346-4763-4037-bba4-cf0dc3447974
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# &lt; iomanip &gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`iostreams` 표준 헤더 `<iomanip>`를 포함하여 각각 단일 인수를 사용하는 여러 조작자를 정의합니다.  
  
## 구문  
  
```  
  
#include <iomanip>  
  
```  
  
## 설명  
 이러한 조작자는 각각 **T1**부터 **T10**까지라는 지정되지 않은 형식을 반환하며 `basic_istream`\<**Elem**, **Tr**\>`::`[operator\>\>](../Topic/operator%3E%3E%20\(%3Cistream%3E\).md) 및 `basic_ostream`\<**Elem**, **Tr**\>`::`[operator\<\<](../Topic/operator%3C%3C%20\(%3Costream%3E\).md)를 오버로드합니다.  
  
### 조작자  
  
|||  
|-|-|  
|[get\_money](../Topic/%3Ciomanip%3E%20get_money.md)|통화 금액을 필요에 따라 국가별 형식으로 가져옵니다.|  
|[get\_time](../Topic/%3Ciomanip%3E%20get_time.md)|지정된 형식으로 사용하여 시간 구조의 시간을 가져옵니다.|  
|[put\_money](../Topic/%3Ciomanip%3E%20put_money.md)|통화 금액을 필요에 따라 국가별 형식으로 제공합니다.|  
|[put\_time](../Topic/%3Ciomanip%3E%20put_time.md)|시간 구조의 시간 및 사용할 형식 문자열을 제공합니다.|  
|[quoted](../Topic/quoted.md)|삽입 및 추출 연산자를 사용하여 문자열의 편리한 라운드트립을 사용하도록 설정합니다.|  
|[resetiosflags](../Topic/resetiosflags.md)|지정된 플래그를 지웁니다.|  
|[setbase](../Topic/setbase.md)|정수의 밑을 설정합니다.|  
|[setfill](../Topic/setfill.md)|오른쪽 맞춤된 디스플레이에서 공백을 채우는데 사용할 문자를 설정합니다.|  
|[setiosflags](../Topic/setiosflags.md)|지정된 플래그를 설정합니다.|  
|[setprecision](../Topic/setprecision.md)|부동 소수점 값의 전체 자릿수를 설정합니다.|  
|[setw](../Topic/setw.md)|표시 필드의 너비를 지정합니다.|  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream 프로그래밍](../standard-library/iostream-programming.md)   
 [iostreams 규칙](../standard-library/iostreams-conventions.md)