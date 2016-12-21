---
title: "컴파일러 경고(수준 4) C4932 | Microsoft Docs"
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
  - "C4932"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4932"
ms.assetid: 0b8d88cc-21f6-45cb-a9f5-1795b7db0dfa
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고(수준 4) C4932
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\_\_identifier\(identifier\)와 \_\_identifier\(identifier\)를 구별할 수 없습니다.  
  
 컴파일러에서 **\_finally** 및 `__finally` 또는 `__try` 및 **\_try**를 [\_\_identifier](../../windows/identifier-cpp-cli.md)에 전달된 매개 변수로 구별할 수 없습니다.[C2374](../../error-messages/compiler-errors-1/compiler-error-c2374.md) 오류가 발생하므로 동일한 프로그램에서 둘 다를 식별자로 사용해서는 안 됩니다.  
  
 다음 샘플에서는 C4932를 생성합니다.  
  
```  
// C4932.cpp // compile with: /clr /W4 /WX int main() { int __identifier(_finally) = 245;   // C4932 int __identifier(__finally) = 25;   // C4932 }  
```