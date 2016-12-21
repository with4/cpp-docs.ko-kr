---
title: "컴파일러 오류 C3080 | Microsoft Docs"
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
  - "C3080"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3080"
ms.assetid: ff62a3f7-9b3b-44bd-b8d9-f3a8e5354560
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3080
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'finalizer\_function': 종료자에는 저장소 클래스 지정자를 사용할 수 없습니다.  
  
 자세한 내용은 [Visual C\+\+의 소멸자 및 종료자](../../misc/destructors-and-finalizers-in-visual-cpp.md)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 C3080을 생성합니다.  
  
```  
// C3080.cpp // compile with: /clr /c ref struct rs { protected: static !rs(){}   // C3080 !rs(){}   // OK };  
```