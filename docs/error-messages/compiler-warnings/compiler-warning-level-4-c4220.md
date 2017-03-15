---
title: "컴파일러 경고 (수준 4) C4220 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4220"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4220"
ms.assetid: aba18868-825f-4763-9af6-3296406a80e4
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 4) C4220
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

varargs는 나머지 매개 변수와 일치합니다.  
  
 기본 Microsoft 확장\(\/Ze\)에서 함수에 대한 포인터는, 비슷하지만 가변적이지 않은 인수가 있는 함수에 대한 포인터와 일치합니다.  
  
## 예제  
  
```  
// C4220.c  
// compile with: /W4  
  
int ( *pFunc1) ( int a, ... );  
int ( *pFunc2) ( int a, int b);  
  
int main()  
{  
   if ( pFunc1 != pFunc2 ) {};  // C4220  
}  
```  
  
 이러한 포인터는 ANSI 규격\([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\)에서는 일치하지 않습니다.