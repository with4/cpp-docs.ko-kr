---
title: 컴파일러 오류 C2425 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2425
dev_langs:
- C++
helpviewer_keywords:
- C2425
ms.assetid: 0ce59404-9aff-4e01-aa8d-27d23e92eb30
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ce9984273ba689bdabe6d1ad6c3c4eb96e151227
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33196859"
---
# <a name="compiler-error-c2425"></a>컴파일러 오류 C2425
'token': 'context'에 비상수 식이 있습니다.  
  
 이 컨텍스트에서 토큰이 비상수 식의 일부를 형성합니다.  
  
 이 문제를 해결하려면 토큰을 상수 리터럴 또는 계산으로 바꿉니다.  
  
 다음 샘플에서는 C2425 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2425.cpp  
// processor: x86  
int main() {  
   int i = 3;  
   __asm {  
      mov eax, [ebp - i]   // C2425  
      mov eax, [ebp - 3]   // OK  
   }  
}  
```