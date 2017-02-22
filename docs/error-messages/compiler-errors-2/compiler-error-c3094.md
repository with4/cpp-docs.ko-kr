---
title: "컴파일러 오류 C3094 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3094"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3094"
ms.assetid: 10da9b7c-e72d-4013-9925-c83e1bb142db
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C3094
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'attribute': 익명으로 사용할 수 없습니다.  
  
 특성의 범위를 올바르게 지정하지 않았습니다.  자세한 내용은 [User\-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 C3094를 생성합니다.  
  
```  
// C3094.cpp // compile with: /clr /c using namespace System; [AttributeUsage(AttributeTargets::Class)] public ref class AAttribute : Attribute {}; [A];   // C3094 // OK [A] ref class x{};  
```