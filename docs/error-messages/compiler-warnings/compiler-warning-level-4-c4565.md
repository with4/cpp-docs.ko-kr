---
title: "컴파일러 경고 (수준 4) C4565 | Microsoft Docs"
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
  - "C4565"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4565"
ms.assetid: a71f1341-a4a1-4060-ad1e-9322531883ed
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 4) C4565
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 재정의: 해당 기호는 이전에 \_\_declspec\(modifier\)로 선언되었습니다.  
  
 기호가 다시 정의되거나 다시 선언되었지만, 첫 번째 정의 또는 선언과는 달리 두 번째 정의 또는 선언에 `__declspec` 한정자\(***modifier***\)가 없습니다.  이 경고는 정보를 제공하기 위한 것입니다.  이 경고를 해결하려면 정의 중 하나를 삭제해야 합니다.  
  
 다음 샘플에서는 C4565 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4565.cpp  
// compile with: /W4 /LD  
__declspec(noalias) void f();  
void f();   // C4565  
```