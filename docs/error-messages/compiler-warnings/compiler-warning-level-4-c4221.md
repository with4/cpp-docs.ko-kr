---
title: "컴파일러 경고 (수준 4) C4221 | Microsoft Docs"
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
  - "C4221"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4221"
ms.assetid: 8532bd68-54dc-4526-8597-f61dcb0a0129
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 4) C4221
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

비표준 확장이 사용됨 : 'identifier' : 자동 변수의 주소를 사용하여 초기화할 수 없습니다.  
  
 기본 Microsoft 확장\(\/Ze\)을 사용하면 **array**, `struct`, **union** 등의 집합체 형식을 지역\(자동\) 변수의 주소를 사용하여 초기화할 수 있습니다.  
  
## 예제  
  
```  
// C4221.c  
// compile with: /W4  
struct S  
{  
   int *i;  
};  
  
void func()  
{  
   int j;  
   struct S s1 = { &j };   // C4221  
}  
  
int main()  
{  
}  
```  
  
 이러한 초기화는 ANSI 규격\([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\)에서는 사용할 수 없습니다.