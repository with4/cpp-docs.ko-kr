---
title: "컴파일러 경고(수준 1) C4794 | Microsoft Docs"
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
  - "C4794"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4794"
ms.assetid: badc9c36-fa1a-4fec-929b-7bfda7a7b79f
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고(수준 1) C4794
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스레드 로컬 저장소 변수 'variable'의 세그먼트가 'section name'에서 '.tls$'로 변경되었습니다.  
  
 .tls$로 시작하지 않는 섹션에 tls 변수를 넣기 위해 [\#pragma data\_seg](../../preprocessor/data-seg.md)를 사용했습니다.  
  
 .tls$*x* 섹션은 [\_\_declspec \(thread\)](../../cpp/thread.md) 변수가 정의된 개체 파일에 있습니다. EXE 또는 DLL의 .tls 섹션은 다음 섹션에서 발생합니다.  
  
## 예제  
 다음 샘플에서는 C4794를 생성합니다.  
  
```  
// C4794.cpp // compile with: /W1 /c #pragma data_seg(".someseg") __declspec(thread) int i;   // C4794 // OK #pragma data_seg(".tls$9") __declspec(thread) int j;  
```