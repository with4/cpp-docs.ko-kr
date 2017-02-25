---
title: "컴파일러 경고 C4950 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4950"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4950"
ms.assetid: 50226a5c-c664-4d09-ac59-e9e874ca244f
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 컴파일러 경고 C4950
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type\_or\_member': 사용되지 않는 것으로 표시되었습니다.  
  
 멤버 또는 형식이 [ObsoleteAttribute](frlrfSystemObsoleteAttributeClassTopic)에서 사용되지 않는 것으로 표시되었습니다.  
  
 C4950은 항상 오류로 실행됩니다.`#pragma warning` 또는 **\/wd**를 사용하여 이 경고를 해제할 수 있습니다. 자세한 내용은 [경고](../../preprocessor/warning.md) 또는 [\/w, \/Wn, \/WX, \/Wall, \/wln, \/wdn, \/wen, \/won\(경고 수준\)](../../build/reference/compiler-option-warning-level.md)을 참조하세요.  
  
 다음 샘플에서는 C4950을 생성합니다.  
  
```  
// C4950.cpp // compile with: /clr using namespace System; // Any reference to Func3 should generate an error with message [System::ObsoleteAttribute("Will be removed in next version", true)] Int32 Func3(Int32 a, Int32 b) { return (a + b); } int main() { Int32 MyInt3 = ::Func3(2, 2);   // C4950 }  
```