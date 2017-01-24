---
title: "컴파일러 경고(수준 3) C4637 | Microsoft Docs"
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
  - "C4637"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4637"
ms.assetid: 5fd347c1-2de9-408f-9136-1bf1ff273622
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고(수준 3) C4637
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

XML 문서 주석 target: \<include\> 태그가 삭제되었습니다.  이유  
  
 [\<include\>](../../ide/include-visual-cpp.md) 태그 구문이 올바르지 않습니다.  
  
 다음 샘플에서는 C4637을 생성합니다.  
  
```  
// C4637.cpp // compile with: /clr /doc /LD /W3 using namespace System; /// Text for class MyClass. public ref class MyClass { public: /// <include file="c:\davedata\jtest\xml_include.doc"/> // Try the following line instead: // /// <include file='xml_include.doc' path='MyDocs/MyMembers/*' /> void MyMethod() { } };   // C4637  
```