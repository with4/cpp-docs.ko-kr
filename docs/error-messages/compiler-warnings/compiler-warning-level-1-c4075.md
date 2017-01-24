---
title: "컴파일러 경고(수준 1) C4075 | Microsoft Docs"
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
  - "C4075"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4075"
ms.assetid: 19a700b6-f210-4b9d-a2f2-76cfe39ab178
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고(수준 1) C4075
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이니셜라이저가 인식할 수 없는 초기화 영역에 있습니다.  
  
 [\#pragma init\_seg](../../preprocessor/init-seg.md)에서는 인식할 수 없는 섹션 이름을 사용합니다. 컴파일러는 **pragma** 명령을 무시합니다.  
  
 다음 샘플에서는 C4075를 생성합니다.  
  
```  
// C4075.cpp // compile with: /W1 #pragma init_seg("mysegg")   // C4075 // try.. // #pragma init_seg(user) int main() { }  
```