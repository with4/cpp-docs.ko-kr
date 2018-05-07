---
title: 컴파일러 오류 C3320 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3320
dev_langs:
- C++
helpviewer_keywords:
- C3320
ms.assetid: 2ef72d9a-1f1d-4b2e-b244-9fd3f3e70cb6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 08810d38b74081cfb8573d1e33ea3a8ec4dabd4c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3320"></a>컴파일러 오류 C3320
'type': 형식은 모듈의 'name' 속성과 같은 이름을 사용할 수 없습니다.  
  
에 전달 된 매개 변수는 내보낸된 사용자 정의 형식 (UDT), 구조체, 클래스, 열거형 또는 공용 구조체 수 있습니다. 같은 이름을 가질 수 없습니다는 [모듈](../../windows/module-cpp.md) 특성의 name 속성입니다.  
  
## <a name="example"></a>예제  
다음 샘플에서는 C3320을 생성합니다.  
  
```cpp  
// C3320.cpp  
#include "unknwn.h"  
[module(name="xx")];  
  
[export] struct xx {   // C3320  
// Try the following line instead  
// [export] struct yy {  
   int i;  
};  
```