---
title: 컴파일러 경고 (수준 1) C4581 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4581
dev_langs:
- C++
helpviewer_keywords:
- C4581
ms.assetid: 598bcd87-257d-4eb3-94e4-15bb31aadc99
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 415fb9ffc3e53ddfe9edcee2ec99361b38de0dea
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4581"></a>컴파일러 경고(수준 1) C4581
사용 되지 않는 동작: '"string1" ' '문자열 2' 프로세스 특성으로 대체  
  
 이 오류는 Visual c + + 2005에 대해 수행한 컴파일러 규칙 작업의 결과로 생성 될 수 있습니다: 매개 변수 Visual c + + 특성에 대 한 검사 합니다.  
  
 이전 버전에서는 특성 값은 따옴표로 묶여 있는지 여부 허용 되었습니다. 열거형 값을 사용 하는 경우 하지 따옴표에 포함 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4581 오류가 발생 합니다.  
  
```  
// C4581.cpp  
// compile with: /c /W1  
#include "unknwn.h"  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IMyI : IUnknown {};  
  
[coclass, uuid(12345678-1111-2222-3333-123456789012), threading("free")]   // C4581  
// try the following line instead  
// [coclass, uuid(12345678-1111-2222-3333-123456789012), threading(free)]  
class CSample : public IMyI {};  
```