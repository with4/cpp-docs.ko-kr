---
title: "컴파일러 오류 C2861 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2861
dev_langs:
- C++
helpviewer_keywords:
- C2861
ms.assetid: 012bb44d-6c9b-4def-b54e-b19f1f8ddd1b
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 18c51d01b8f273d4546f3411405fe511e31799ef
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2861"></a>컴파일러 오류 C2861
'함수 name': 인터페이스 멤버 함수를 정의할 수 없습니다  
  
 컴파일러 인터페이스 키워드 발생 또는 인터페이스 구조체 추론 되었으나 멤버를 찾을 수 함수 정의 합니다.  인터페이스는 멤버 함수에 대 한 정의 포함할 수 없습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2861 오류가 생성 됩니다.  
  
```  
// C2861.cpp  
// compile with: /c  
#include <objbase.h>   // required for IUnknown definition  
[ object, uuid("00000000-0000-0000-0000-000000000001") ]  
__interface IMyInterface : IUnknown {  
   HRESULT mf(int a);  
};  
  
HRESULT IMyInterface::mf(int a) {}   // C2861  
  
```
