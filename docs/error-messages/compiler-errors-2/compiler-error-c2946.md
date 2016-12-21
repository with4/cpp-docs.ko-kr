---
title: "컴파일러 오류 C2946 | Microsoft Docs"
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
  - "C2946"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2946"
ms.assetid: c86dfbfc-7702-4f09-8a53-d205710e99c2
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2946
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

명시적 인스턴스화. 'class'는 템플릿\-클래스 특수화가 아닙니다.  
  
 템플릿이 아닌 클래스를 명시적으로 인스턴스화할 수 없습니다.  
  
## 예제  
 다음 샘플에서는 C2946을 생성합니다.  
  
```  
// C2946.cpp class C {}; template C;  // C2946 int main() {}  
```