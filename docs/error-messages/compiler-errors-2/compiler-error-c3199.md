---
title: "컴파일러 오류 C3199 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3199"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3199"
ms.assetid: e7a478d3-115a-40a3-991b-c7454fd2e28e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3199
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

부동 소수점 pragma를 잘못 사용했습니다. precise 모드가 아닌 모드에서는 예외가 지원되지 않습니다.  
  
 **\/fp:precise** 이외의 [\/fp](../../build/reference/fp-specify-floating-point-behavior.md) 설정을 사용하여 부동 소수점 예외 모델을 지정하는 데 [float\_control](../../preprocessor/float-control.md) pragma를 사용했습니다.  
  
 다음 샘플에서는 C3199 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3199.cpp  
// compile with: /fp:fast  
#pragma float_control(except, on)   // C3199  
```