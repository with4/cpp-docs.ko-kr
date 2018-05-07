---
title: 컴파일러 오류 C2861 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2861
dev_langs:
- C++
helpviewer_keywords:
- C2861
ms.assetid: 012bb44d-6c9b-4def-b54e-b19f1f8ddd1b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4e1f7010ca6d98c4c27f85ecc858cf7703a87e90
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
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