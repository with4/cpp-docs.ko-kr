---
title: "컴파일러 경고 (수준 4) C4213 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4213"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4213"
ms.assetid: 59fc3f61-ebd2-499e-99d7-f57bec11eda1
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 4) C4213
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

비표준 확장을 사용했습니다 : l\-value를 캐스팅했습니다.  
  
 기본 Microsoft 확장\(\/Ze\)을 사용하면 할당문의 왼쪽을 캐스팅할 수 있습니다.  
  
## 예제  
  
```  
// C4213.c  
// compile with: /W4  
void *a;  
void f()  
{  
   int   i[3];  
   a = &i;  
   *(( int * )a )++ = 3;  // C4213  
}  
  
int main()  
{  
}  
```  
  
 이러한 캐스트는 ANSI 규격\([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\)에서는 사용할 수 없습니다.