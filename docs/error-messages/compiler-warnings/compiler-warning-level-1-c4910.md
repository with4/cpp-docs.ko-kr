---
title: "컴파일러 경고(수준 1) C4910 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4910"
ms.assetid: 67963560-fbca-4ca7-93db-06beaf7055f0
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# 컴파일러 경고(수준 1) C4910
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\<identifier\>' : '\_\_declspec\(dllexport\)' 및 'extern'이 명시적 인스턴스화에서 호환되지 않습니다.  
  
 *\<identifier\>*라는 명시적 템플릿 인스턴스화가 `__declspec(dllexport)` 및 `extern` 키워드 둘 다로 수정됩니다. 그러나 이러한 키워드는 함께 사용할 수 없습니다.`__declspec(dllexport)` 키워드는 템플릿 클래스의 인스턴스화를 의미하는 반면, `extern` 키워드는 템플릿 클래스를 자동으로 인스턴스화하지 않음을 의미합니다.  
  
## 참고 항목  
 [명시적 인스턴스화](../../cpp/explicit-instantiation.md)   
 [dllexport, dllimport](../../cpp/dllexport-dllimport.md)   
 [일반 규칙 및 제한](../../cpp/general-rules-and-limitations.md)