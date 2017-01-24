---
title: "컴파일러 오류 C3320 | Microsoft Docs"
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
  - "C3320"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3320"
ms.assetid: 2ef72d9a-1f1d-4b2e-b244-9fd3f3e70cb6
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3320
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': 형식은 모듈의 'name' 속성과 같은 이름을 사용할 수 없습니다.  
  
 구조체, 클래스, 열거형, 공용 구조체 또는 [\_\_value](../../misc/value.md)일 수 있는 내보낸 UDT\(사용자 정의 형식\)에서 [module](../../windows/module-cpp.md) 특성의 이름 속성에 전달된 매개 변수와 동일한 이름을 사용할 수 없습니다.  
  
 다음 샘플에서는 C3320을 생성합니다.  
  
```  
// C3320.cpp #include "unknwn.h" [module(name="xx")]; [export] struct xx {   // C3320 // Try the following line instead // [export] struct yy { int i; };  
```