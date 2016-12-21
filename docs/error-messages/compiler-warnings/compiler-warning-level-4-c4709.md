---
title: "컴파일러 경고 (수준 4) C4709 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4709"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4709"
ms.assetid: 8abfdd45-8c70-4c27-b0fb-ca0c3f0fccf9
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 4) C4709
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

배열 인덱스 식 내에 쉼표 연산자가 있습니다.  
  
 배열 인덱스 식에 쉼표가 있으면 컴파일러에서는 마지막 쉼표 뒤에 있는 값을 사용합니다.  
  
## 예제  
 다음 샘플에서는 C4709 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4709.cpp  
// compile with: /W4  
#include <stdio.h>  
  
int main()   
{  
    int arr[2][2];  
    arr[0][0] = 10;  
    arr[0][1] = 11;  
  
    // Prints 10, not 11  
    printf_s("\n%d",arr[0][1,0]);   // C4709  
}  
```