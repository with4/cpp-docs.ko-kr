---
title: "프로그램 종료 시 return 문 (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "데이터 형식[C++], 함수 반환 형식"
  - "함수 반환 형식, return 문"
  - "return 키워드[C++], 구문"
ms.assetid: 66d002ab-5625-4b68-8446-71e1b8fcdbd8
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 프로그램 종료 시 return 문 (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**main**에서 `return` 문을 실행하는 것은 **exit** 함수를 호출하는 것과 기능적으로 동일합니다.  다음 예제를 참조하십시오.  
  
```  
// return_statement.cpp  
#include <stdlib.h>  
int main()  
{  
    exit( 3 );  
    return 3;  
}  
```  
  
 위의 예제에서 **exit** 및 `return` 문은 기능적으로 동일합니다.  그러나 C\+\+에서는 `void`가 아닌 반환 형식을 가지는 함수가 값을 반환해야 합니다.  `return` 문을 사용하면 **main**에서 값을 반환할 수 있습니다.  
  
## 참고 항목  
 [프로그램 종료](../cpp/program-termination.md)