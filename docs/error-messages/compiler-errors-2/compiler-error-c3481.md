---
title: "컴파일러 오류 C3481 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3481"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3481"
ms.assetid: 5d09375a-5ed3-4b61-86ed-45e91fd734c7
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3481
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var': 람다 캡처 변수가 없습니다.  
  
 컴파일러가 람다 식의 캡처 목록에 전달된 변수 정의를 찾을 수 없습니다.  
  
### 이 오류를 해결하려면  
  
-   람다 식의 캡처 목록에서 변수를 제거합니다.  
  
## 예제  
 다음 예제에서는 `n` 변수가 정의되지 않았기 때문에 C3481을 생성합니다.  
  
```  
// C3481.cpp int main() { [n] {}(); // C3481 }  
```  
  
## 참고 항목  
 [람다 식](../../cpp/lambda-expressions-in-cpp.md)