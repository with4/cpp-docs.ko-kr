---
title: "컴파일러 오류 C3296 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3296"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3296"
ms.assetid: fc4c9dcd-16cf-4eee-a1ac-c43e7c29e443
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# 컴파일러 오류 C3296
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'property': 같은 이름의 속성이 이미 있습니다.  
  
 컴파일러가 동일한 이름의 속성을 둘 이상 발견했습니다. 형식의 각 속성에는 고유한 이름이 있어야 합니다.  
  
 자세한 내용은 [property](../../windows/property-cpp-component-extensions.md)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 C3296을 생성합니다.  
  
```  
// C3296.cpp // compile with: /clr /c using namespace System; ref class R { public: property int MyProp[int] { int get(int); } property String^ MyProp[int] { void set(int, String^); }   // C3296 };  
```