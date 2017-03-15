---
title: "컴파일러 오류 C3295 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3295"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3295"
ms.assetid: 83f0aa4d-0e0a-4905-9f66-fcf9991fc07a
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# 컴파일러 오류 C3295
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\#pragma pragma'는 전역 또는 네임스페이스 범위에서만 사용할 수 있습니다.  
  
 일부 pragma는 함수에 사용할 수 없습니다.  자세한 내용은 [Pragma 지시문 및 \_\_Pragma 키워드](../../preprocessor/pragma-directives-and-the-pragma-keyword.md)를 참조하세요.  
  
## 예제  
 다음 샘플에서는 C3295를 생성합니다.  
  
```  
// C3295.cpp int main() { #pragma managed   // C3295 }  
```