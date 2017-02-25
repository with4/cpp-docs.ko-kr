---
title: "while 문 (C) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "while"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "while 키워드[C]"
  - "while 키워드[C], 구문"
ms.assetid: d0c970b8-12a9-4827-afb2-a051111834b7
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# while 문 (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`while` 문을 사용하면 지정된 식이 false가 될 때까지 문을 반복할 수 있습니다.  
  
## 구문  
 *iteration\-statement*:  
 **while \(**  *expression*  **\)**  *statement*  
  
 *expression*은 산술 형식이나 포인터 형식이어야 합니다.  다음과 같이 실행됩니다.  
  
1.  *expression*이 계산됩니다.  
  
2.  *expression*이 처음에 false인 경우 `while` 문의 본문이 실행되지 않으며, `while` 문에서 프로그램의 다음 문으로 제어가 전달됩니다.  
  
     *expression*이 true\(0이 아님\)인 경우 문의 본문이 실행되고 1단계부터 반복됩니다.  
  
 `while` 문 본문 안에 있는 **break**, `goto` 또는 `return`이 실행될 때 while 문도 종료될 수 있습니다.  `while` 루프를 종료하지 않고 반복을 종료하려면 **continue** 문을 사용합니다.  **continue** 문은 `while` 문의 다음 반복으로 제어를 전달합니다.  
  
 다음은 `while` 문의 예제입니다.  
  
```  
while ( i >= 0 )   
{  
    string1[i] = string2[i];  
    i--;  
}  
```  
  
 이 예제에서는 `string2`의 문자를 `string1`에 복사합니다.  `i`가 0보다 크거나 같은 경우 `string2[i]`가 `string1[i]`에 할당되고 `i`는 감소합니다.  `i`가 0에 도달하거나 0 미만이면 `while` 문의 실행이 종료됩니다.  
  
## 참고 항목  
 [while 문 \(C\+\+\)](../cpp/while-statement-cpp.md)