---
title: "컴파일러 경고 (수준 1) C4405 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4405
dev_langs: C++
helpviewer_keywords: C4405
ms.assetid: 155c64d6-58ae-4455-b61f-ccd711c5da96
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b20bde360df28158ad504739a1de10d90e3ef0cb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4405"></a>컴파일러 경고(수준 1) C4405
'identifier': 식별자가 예약어  
  
 인라인 어셈블리에 대 한 예약 된 단어를 변수 이름으로 사용 됩니다. 이 예상치 못한 결과가 발생할 수 있습니다. 이 경고를 해결 하려면 변수를 명명 인라인 어셈블리에 대 한 예약 된 단어를 포함 하지 마십시오. 다음 샘플에서는 C4405 오류가 생성 됩니다.  
  
```  
// C4405.cpp  
// compile with: /W1  
// processor: x86  
void func1() {  
   int mov = 0, i = 0;  
   _asm {  
      mov mov, 0;   // C4405  
      // instead, try ..  
      // mov i, 0;  
   }  
}  
  
int main() {  
}  
```