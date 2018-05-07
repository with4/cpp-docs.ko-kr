---
title: 컴파일러 경고 (수준 1) C4722 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4722
dev_langs:
- C++
helpviewer_keywords:
- C4722
ms.assetid: d8660710-f67b-4f59-a5fd-59259475529e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 143a902a4d05ab73df96f3f8ab35f52dab244df4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4722"></a>컴파일러 경고(수준 1) C4722
'function': 소멸자가 반환하지 않습니다. 메모리 누수가 발생할 수 있습니다.  
  
 제어 흐름이 소멸자에서 종료됩니다. 스레드 또는 전체 프로그램이 종료되고 할당된 리소스를 해제할 수 없습니다.  또한 예외 처리 중 스택 해제를 위해 소멸자가 호출될 경우 실행 파일의 동작이 정의되지 않습니다.  
  
 이 문제를 해결하려면 소멸자 반환을 방해하는 함수 호출을 제거합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4722를 생성합니다.  
  
```  
// C4722.cpp  
// compile with: /O1 /W1 /c  
#include <stdlib.h>  
class C {  
public:  
   C();  
   ~C() { exit(1); };   // C4722  
};  
  
extern void func (C*);  
  
void Test(){  
   C x;  
   func(&x);  
   // control will not leave Test because destructor will exit  
}  
```