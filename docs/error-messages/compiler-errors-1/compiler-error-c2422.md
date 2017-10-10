---
title: "컴파일러 오류 C2422 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2422
dev_langs:
- C++
helpviewer_keywords:
- C2422
ms.assetid: ef0ec302-4028-4778-b134-0b8cea4bcad9
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 65412576c3c1a5e6b8205652d826d0eca6d222e6
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2422"></a>컴파일러 오류 C2422
'피연산자'에 잘못 된 세그먼트 재정의가 있습니다.  
  
 인라인 어셈블리 코드 올바르게에서 사용 했습니다 세그먼트 재정의 (콜론) 연산자를 피연산자입니다.  이 오류가 발생하는 원인은 다음과 같습니다.  
  
-   연산자 앞에 오는 레지스터가 세그먼트 레지스터가 아닙니다.  
  
-   연산자 앞에 오는 레지스터가 피연산자의 유일한 세그먼트 레지스터가 아닙니다.  
  
-   세그먼트 재정의 연산자 간접 참조 연산자 (괄호) 내에 나타납니다.  
  
-   세그먼트 재정의 연산자 다음에 나오는 식 직접 피연산자 또는 메모리 피연산자 아닙니다.  
  
 다음 샘플에서는 C2422 오류가 생성 됩니다.  
  
```  
// C2422.cpp  
// processor: x86  
int main() {  
   _asm {  
      mov AX, [BX:ES]   // C2422  
      mov AX, ES   // OK  
   }  
}  
```
