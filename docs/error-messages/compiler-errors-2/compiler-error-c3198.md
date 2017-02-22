---
title: "컴파일러 오류 C3198 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3198"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3198"
ms.assetid: ec4ecf61-0067-4aa4-b443-a91013a1e59d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C3198
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

부동 소수점 pragma를 잘못 사용했습니다. fenv\_access pragma는 precise 모드에서만 작동합니다.  
  
 [fenv\_access](../../preprocessor/fenv-access.md) pragma를 **\/fp:precise** 이외의 [\/fp](../../build/reference/fp-specify-floating-point-behavior.md) 설정과 함께 사용했습니다.  
  
 다음 샘플에서는 C3198 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3198.cpp  
// compile with: /fp:fast  
#pragma fenv_access(on)   // C3198  
```