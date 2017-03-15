---
title: "컴파일러 경고 (수준 3) C4334 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4334"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4334"
ms.assetid: d845857f-bc95-4faf-a079-626a0cf935ba
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 경고 (수준 3) C4334
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator' : 32비트 시프트의 결과가 암시적으로 64비트로 변환됩니다. 64비트 시프트를 사용하시겠습니까?  
  
 32비트 시프트의 결과가 암시적으로 64비트로 변환되었습니다. 컴파일러에서 64비트 시프트의 적용 여부를 결정할 수 없습니다.  이 경고를 해결하려면 64비트 시프트를 사용하거나 시프트 결과를 명시적으로 64비트로 캐스팅해야 합니다.  
  
## 예제  
 다음 샘플에서는 C4334 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4334.cpp  
// compile with: /W3 /c  
void SetBit(unsigned __int64 *p, int i) {  
   *p |= (1 << i);   // C4334  
   *p |= (1i64 << i);   // OK  
}  
```