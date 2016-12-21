---
title: "컴파일러 경고 C4972 | Microsoft Docs"
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
  - "C4972"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4972"
ms.assetid: d18e8e65-b2ef-4d75-a207-fbd0c17c9060
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 C4972
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

왼쪽 항의 값\(l\-value\)을 확인할 수 없어 unboxing 작업의 결과를 직접 수정하거나 처리하고 있습니다.  
  
 핸들을 값 형식으로 역참조\(unboxing이라고도 함\)한 후 할당하는 작업을 확인할 수 없습니다.  
  
 자세한 내용은 [Boxing](../../windows/boxing-cpp-component-extensions.md)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 C4972를 생성합니다.  
  
```  
// C4972.cpp // compile with: /clr:safe using namespace System; ref struct R { int ^ p;   // a value type }; int main() { R ^ r = gcnew R; *(r->p) = 10;   // C4972 // OK r->p = 10; Console::WriteLine( r->p ); Console::WriteLine( *(r->p) ); }  
```