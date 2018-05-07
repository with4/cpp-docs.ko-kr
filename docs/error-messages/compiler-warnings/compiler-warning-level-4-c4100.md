---
title: 컴파일러 경고 (수준 4) C4100 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4100
dev_langs:
- C++
helpviewer_keywords:
- C4100
ms.assetid: 478ed97d-e502-49e4-9afb-ac2a6c61194b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d3cf831590af2e1f2f7cd13d93c9d13ba217e11
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4100"></a>컴파일러 경고(수준 4) C4100
'identifier': 참조 되지 않은 형식 매개 변수  
  
 형식 매개 변수는 함수의 본문에서 참조 하지 않습니다. 참조 되지 않은 매개 변수는 무시 됩니다.  
  
 코드에서 소멸자를 호출할 때 C4100 발급할 수도 있습니다는 참조 되지 않는 기본 형식의 매개 변수입니다.  Visual c + + 컴파일러의 제한 사항입니다.  
  
 다음 샘플에서는 C4100 오류가 생성 됩니다.  
  
```  
// C4100.cpp  
// compile with: /W4  
void func(int i) {   // C4100, delete the unreferenced parameter to  
                     //resolve the warning  
   // i;   // or, add a reference like this  
}  
  
int main()  
{  
   func(1);  
}  
```