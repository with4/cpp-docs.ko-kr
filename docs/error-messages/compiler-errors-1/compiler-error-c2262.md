---
title: "컴파일러 오류 C2262 | Microsoft Docs"
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
  - "C2262"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2262"
ms.assetid: 727d1c6e-53e8-40e5-b7b8-6a7ac2011727
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2262
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'attribute\_specifiers': InternalsVisibleTo 선언에는 버전, 문화권 또는 프로세서 아키텍처를 지정할 수 없습니다.  
  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성을 올바르게 지정하지 않았습니다.  
  
## 예제  
 다음 샘플에서는 C2262를 생성합니다.  
  
```  
// C2262.cpp // compile with: /clr /c using namespace System::Runtime::CompilerServices; [assembly: InternalsVisibleTo("assembly_name, version=1.2.3.7")];   // C2262 [assembly: InternalsVisibleTo("assembly_name ")];   // OK  
```