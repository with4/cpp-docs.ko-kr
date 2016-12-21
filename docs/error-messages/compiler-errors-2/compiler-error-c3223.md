---
title: "컴파일러 오류 C3223 | Microsoft Docs"
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
  - "C3223"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3223"
ms.assetid: 1f4380b4-0413-40db-a868-62f97babaf78
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3223
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'property': 속성에 'typeid'를 적용할 수 없습니다.  
  
 속성에 [typeid](../../windows/typeid-cpp-component-extensions.md)를 적용할 수 없습니다.  
  
## 예제  
 다음 샘플에서는 C3223을 생성합니다.  
  
```  
// C3223.cpp // compile with: /clr ref class R { public: property int myprop; }; int main() { System::Type^ type2 = R::myprop::typeid;   // C3223 }  
```