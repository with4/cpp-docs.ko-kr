---
title: "컴파일러 오류 C3291 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3291"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3291"
ms.assetid: ed2e9f89-8dbc-4387-bc26-cc955e840858
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# 컴파일러 오류 C3291
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'default' : trivial 속성의 이름이 될 수 없습니다.  
  
 trivial 속성은 `default`로 이름을 바꿀 수 없습니다. 자세한 내용은 [property](../../windows/property-cpp-component-extensions.md)를 참조하세요.  
  
## 예제  
 다음 샘플에서는 C3291을 생성합니다.  
  
```  
// C3291.cpp // compile with: /clr /c ref struct C { property System::String ^ default;   // C3291 property System::String ^ Default;   // OK };  
```