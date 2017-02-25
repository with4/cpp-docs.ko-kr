---
title: "컴파일러 경고 (수준 4) C4214 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4214"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4214"
ms.assetid: 9b8db279-1f12-4a6b-a923-2db22acd1947
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 4) C4214
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

비표준 확장을 사용했습니다 : 비트 필드 형식이 int가 아닙니다.  
  
 기본 Microsoft 확장\(\/Ze\)을 사용하면 비트 필드 구조체 멤버를 정수 계열 형식으로 만들 수 있습니다.  
  
## 예제  
  
```  
// C4214.c  
// compile with: /W4  
struct bitfields  
{  
   unsigned short j:4;  // C4214  
};  
  
int main()  
{  
}  
```  
  
 이러한 비트 필드는 ANSI 규격\([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\)에서는 사용할 수 없습니다.