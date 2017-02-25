---
title: "컴파일러 오류 C3492 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3492"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3492"
ms.assetid: b1dc6342-9133-4b1f-a9c3-e8c65d20d121
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C3492
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var': 익명 공용 구조체의 멤버를 캡처할 수 없습니다.  
  
 명명되지 않은 공용 구조체의 멤버를 캡처할 수 없습니다.  
  
### 이 오류를 해결하려면  
  
-   공용 구조체에 이름을 지정하고 완전한 공용 구조체를 람다 식의 캡처 목록에 전달합니다.  
  
## 예제  
 다음 예제에서는 익명 공용 구조체의 멤버를 캡처하므로 C3492를 생성합니다.  
  
```  
// C3492a.cpp int main() { union { char ch; int x; }; ch = 'y'; [&x](char ch) { x = ch; }(ch); // C3492 }  
```  
  
## 예제  
 다음 예제에서는 공용 구조체에 이름을 지정하고 완전한 공용 구조체를 람다 식의 캡처 목록에 전달하여 C3492를 해결합니다.  
  
```  
// C3492b.cpp int main() { union { char ch; int x; } u; u.ch = 'y'; [&u](char ch) { u.x = ch; }(u.ch); }  
```  
  
## 참고 항목  
 [람다 식](../../cpp/lambda-expressions-in-cpp.md)