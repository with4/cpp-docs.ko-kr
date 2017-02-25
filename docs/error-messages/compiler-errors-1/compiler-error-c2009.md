---
title: "컴파일러 오류 C2009 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2009"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2009"
ms.assetid: fe9d94ed-20a5-4d83-b9c4-60ee69d2f30a
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2009
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

매크로 형식 'identifier'을\(를\) 다시 사용하십시오.  
  
 매크로 정의에 대한 형식 매개 변수 목록은 식별자를 여러 번 사용합니다.  매크로 매개 변수 목록의 식별자는 고유해야 합니다.  
  
## 예제  
 다음 샘플에서는 C2009 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2009.cpp  
#include <stdio.h>  
  
#define macro1(a,a) (a*a)   // C2009  
  
int main()   
{  
    printf_s("%d\n", macro1(2));  
}  
```  
  
## 예제  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C2009b.cpp  
#include <stdio.h>  
  
#define macro2(a)   (a*a)   
#define macro3(a,b) (a*b)  
  
int main()   
{  
    printf_s("%d\n", macro2(2));  
    printf_s("%d\n", macro3(2,4));  
}  
```