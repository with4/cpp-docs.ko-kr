---
title: "true (C++) | Microsoft Docs"
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
  - "true_cpp"
  - "true"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "true 키워드[C++]"
ms.assetid: 96be2a70-51c3-4250-9752-874d25a5a11e
caps.latest.revision: 12
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# true (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
  
        bool-identifier = true ;  
bool-expression logical-operator true ;  
```  
  
## 설명  
 이 키워드는 [bool](../cpp/bool-cpp.md) 형식의 변수 또는 조건식의 값 2개 중 하나입니다. 이제 조건식이 부울 식입니다.  `i`가 `bool` 형식이면 `i = true;` 문이 **에 `i`true**를 할당합니다.  
  
## 예제  
  
```  
// bool_true.cpp  
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