---
title: 컴파일러 오류 C2561 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2561
dev_langs:
- C++
helpviewer_keywords:
- C2561
ms.assetid: 0abe955b-53a6-4a3c-8362-b1a8eb40e8d1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4f8ece9a3d9347a5179844cbfca3425870c25e2f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2561"></a>컴파일러 오류 C2561
'identifier': 함수는 값을 반환 해야 합니다  
  
 함수는 값을 반환 하도록 선언 되었지만 하지만 함수 정의 포함 하지 않는 한 `return` 문.  
  
 이 오류는 잘못 된 함수 프로토타입 원인일 수 있습니다.  
  
1.  함수는 값을 반환 하지 않는, 하는 경우 반환 형식이 있는 함수를 선언할 [void](../../cpp/void-cpp.md)합니다.  
  
2.  함수의 모든 가능한 분기 프로토타입에 선언 된 형식의 값을 반환 함을 확인 합니다.  
  
3.  C + + 함수에서 반환 값을 저장 하는 인라인 어셈블리 루틴을 포함 하는 `AX` 레지스터는 return 문을 할 수 있습니다. 값을 복사 `AX` 임시 변수에 함수에서 해당 변수를 반환 합니다.  
  
 다음 샘플에서는 C2561 오류가 생성 됩니다.  
  
```  
// C2561.cpp  
int Test(int x) {  
   if (x) {  
      return;   // C2561  
      // try the following line instead  
      // return 1;  
   }  
   return 0;  
}  
  
int main() {  
   Test(1);  
}  
```