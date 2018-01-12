---
title: "컴파일러 경고 (수준 1) C4537 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4537
dev_langs: C++
helpviewer_keywords: C4537
ms.assetid: 9454493c-d419-475e-8f35-9c00233c9329
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8cdc3cc00b1b6ea52657f441423e61c3003652ce
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4537"></a>컴파일러 경고(수준 1) C4537
'object': 'operator' 비 UDT 형식에 적용  
  
 대 한 참조는 개체 (사용자 정의 형식) 필요한 위치 전달 되었습니다. 참조는 개체는 있지만 인라인 어셈블러 코드로 위해 그 차이 만들 수 없습니다. 컴파일러에서는 코드 처럼 ***개체*** 인스턴스.  
  
 다음 샘플에서는 C4537 오류가 생성 됩니다.  
  
```  
// C4537.cpp  
// compile with: /W1 /c  
// processor: x86  
struct S {  
   int member;  
};  
  
void f1(S &s) {  
   __asm mov eax, s.member;   // C4537  
   // try the following code instead  
   // or, make the declaration "void f1(S s)"  
   /*  
   mov eax, s  
   mov eax, [eax]s.member  
   */  
}  
```