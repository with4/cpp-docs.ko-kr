---
title: "심각한 오류 C1190 | Microsoft Docs"
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
  - "C1190"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1190"
ms.assetid: dee2266d-6c40-4f6e-91db-f01e65f8d2bc
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 심각한 오류 C1190
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

관리되는 대상 코드에는 '\/clr' 옵션을 사용해야 합니다.  
  
 CLR 구문을 사용하지만 **\/clr**을 지정하지 않았습니다.  
  
 자세한 내용은 [\/clr\(공용 언어 런타임 컴파일\)](../../build/reference/clr-common-language-runtime-compilation.md)을 참조하세요.  
  
 다음 샘플에서는 C1190을 생성합니다.  
  
```  
// C1190.cpp // compile with: /c __gc class A {};   // C1190 ref class A {};  
```