---
title: 컴파일러 경고 (수준 4) C4408 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4408
dev_langs:
- C++
helpviewer_keywords:
- C4408
ms.assetid: 8488a186-ed1d-425c-aaeb-c72472c1da68
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 640a3de24921186bd441b8f8b9bc5f3dcd7e5810
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33297582"
---
# <a name="compiler-warning-level-4-c4408"></a>컴파일러 경고(수준 4) C4408
anonymousstruct 또는 공용 구조체 데이터 멤버를 선언 하지 않았습니다.  
  
 익명 구조체 또는 공용 구조체에 데이터 멤버가 하나 이상 있어야 합니다.  
  
 다음 샘플에서는 C4408 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4408.cpp  
// compile with: /W4 /LD  
static union  
{  
   // int i;  
};  
// a named union can have no data members  
// } MyUnion;  
```