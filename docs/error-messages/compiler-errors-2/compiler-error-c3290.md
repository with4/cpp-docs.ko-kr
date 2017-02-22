---
title: "컴파일러 오류 C3290 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3290"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3290"
ms.assetid: 0baf684b-1143-4953-ac99-a2fa267d8017
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C3290
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': trivial 속성은 참조 형식일 수 없습니다.  
  
 속성이 잘못 선언되었습니다. trivial 속성을 선언하면 컴파일러가 속성에서 업데이트할 변수를 만들며, 클래스에 추적 참조 변수를 사용할 수 없습니다.  
  
 자세한 내용은 [property](../../windows/property-cpp-component-extensions.md) 및 [Tracking Reference Operator](../../windows/tracking-reference-operator-cpp-component-extensions.md)를 참조하세요.  
  
## 예제  
 다음 샘플에서는 C3290을 생성합니다.  
  
```  
// C3290.cpp // compile with: /clr /c ref struct R {}; ref struct X { R^ mr; property R % y;   // C3290 property R ^ x;   // OK // OK property R% prop { R% get() { return *mr; } void set(R%) {} } }; int main() { X x; R% xp = x.prop; }  
```