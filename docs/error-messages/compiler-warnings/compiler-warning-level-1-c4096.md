---
title: 컴파일러 경고 (수준 1) C4096 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4096
dev_langs:
- C++
helpviewer_keywords:
- C4096
ms.assetid: abf3cca2-2f21-45d8-b025-6b513b00681e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3787ef5482841e33658e02371fa0f6d1682612ac
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33276281"
---
# <a name="compiler-warning-level-1-c4096"></a>컴파일러 경고 (수준 1) C4096
'a': 인터페이스는 COM 인터페이스; 아닙니다. IDL로 내보내지 않습니다.  
  
 COM 인터페이스 계획 했던 인터페이스 정의 COM 인터페이스로 정의 되지 않았습니다 고 따라서 내보내지지 않습니다 IDL 파일을 합니다.  
  
 참조 [인터페이스 특성](../../windows/interface-attributes.md) 인터페이스는 COM 인터페이스를 나타내는 특성을 목록에 대 한 합니다.  
  
 다음 샘플에서는 C4096 오류가 생성 됩니다.  
  
```  
// C4096.cpp  
// compile with: /W1 /LD  
#include "windows.h"  
[module(name="xx")];  
  
// [object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface a  
{  
};  
  
[coclass, uuid("00000000-0000-0000-0000-000000000002")]  
struct b : a  
{  
};   // C4096, remove coclass or uncomment object  
```