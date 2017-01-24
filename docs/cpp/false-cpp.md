---
title: "false (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "false_cpp"
  - "false"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "false 키워드[C++]"
ms.assetid: cc13aec5-1f02-4d38-8dbf-5473ea2b354f
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# false (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 키워드는 [bool](../cpp/bool-cpp.md) 형식의 변수나 조건식\(조건식은 이제 **true** 부울 식임\)에 대한 두 값 중 하나입니다.  예를 들어 `i`가 `bool` 형식의 변수인 경우 `i = false;` 문은 **false**를 `i`에 할당합니다.  
  
## 예제  
  
```  
// bool_false.cpp  
#include <stdio.h>  
  
int main()  
{  
    bool bb = true;  
    printf_s("%d\n", bb);  
    bb = false;  
    printf_s("%d\n", bb);  
}  
```  
  
  **1**  
**0**   
## 참고 항목  
 [C\+\+ 키워드](../cpp/keywords-cpp.md)