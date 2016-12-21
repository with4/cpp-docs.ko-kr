---
title: "컴파일러 경고(수준 4) C4634 | Microsoft Docs"
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
  - "C4634"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4634"
ms.assetid: 3e3496ce-2ac7-43d0-a48a-f514c950e81d
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고(수준 4) C4634
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

XML 문서 주석: 적용할 수 없습니다. reason  
  
 일부 C\+\+ 구문에 XML 문서 태그를 적용할 수 없습니다.  예를 들어 네임스페이스 또는 템플릿에 문서 주석을 추가할 수 없습니다.  
  
 자세한 내용은 [XML 문서](../../ide/xml-documentation-visual-cpp.md)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 C4634를 생성합니다.  
  
```  
// C4634.cpp // compile with: /W4 /doc /c /// This is a namespace.   // C4634 namespace hello { class MyClass  {}; };  
```  
  
## 예제  
 다음 샘플에서는 C4634를 생성합니다.  
  
```  
// C4634_b.cpp // compile with: /W4 /doc /c /// This is a template.   // C4634 template <class T> class MyClass  {};  
```