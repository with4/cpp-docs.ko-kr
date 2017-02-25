---
title: "컴파일러 경고 (수준 1) C4508 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4508"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4508"
ms.assetid: c05f113b-b789-4df0-a4ef-78bce4767021
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 1) C4508
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 함수는 값을 반환해야 하므로 'void' 반환 형식으로 간주됩니다.  
  
 함수에 지정된 반환 형식이 없으므로  이 경우 C4430도 발생합니다. 컴파일러는 C4430에 보고된 수정 사항을 구현합니다. 기본값은 int입니다.  
  
 이 경고를 해결하려면 함수의 반환 형식을 명시적으로 선언하십시오.  
  
 다음 샘플에서는 C4508 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4508.cpp  
// compile with: /W1 /c  
#pragma warning (disable : 4430)  
func() {}   // C4508  
void func2() {}   // OK  
```