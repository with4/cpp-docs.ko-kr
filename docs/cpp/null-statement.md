---
title: "Null 문 | Microsoft Docs"
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
  - "식[C++], null"
  - "null 문"
  - "null 값, 식"
ms.assetid: 606f5953-55f0-40c8-ae03-3ee3a819b851
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Null 문
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

"null 문"은 *expression*이 누락된 식 문입니다.  언어의 구문에 문이 필요하지만 식 계산은 필요하지 않은 경우에 이 문이 유용합니다.  이 문은 세미콜론으로 구성됩니다.  
  
 null 문은 일반적으로 반복 문에서 자리 표시자로 사용되거나 복합 문 또는 함수의 끝에 레이블을 배치할 문으로 사용됩니다.  
  
 다음 코드 조각에서는 한 문자열을 다른 문자열로 복사하여 null 문을 통합하는 방법을 보여 줍니다.  
  
```  
// null_statement.cpp  
char *myStrCpy( char *Dest, const char *Source )  
{  
    char *DestStart = Dest;  
  
    // Assign value pointed to by Source to  
    // Dest until the end-of-string 0 is  
    // encountered.  
    while( *Dest++ = *Source++ )  
        ;   // Null statement.  
  
    return DestStart;  
}  
  
int main()  
{  
}  
```  
  
## 참고 항목  
 [식 문](../cpp/expression-statement.md)